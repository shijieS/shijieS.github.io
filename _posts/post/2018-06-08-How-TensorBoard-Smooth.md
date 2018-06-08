---
date: '2018-06-08 08:47 +0800'
published: false
---
Currently, I find if I use a smooth window then I'll get a better result than tensorflow smooth function. So I deep into the smooth function of tensorboard.

Tensorboard smooth function is explained [here](https://github.com/tensorflow/tensorboard/blob/f801ebf1f9fbfe2baee1ddd65714d0bccc640fb1/tensorboard/plugins/scalar/vz_line_chart/vz-line-chart.ts#L55) and used [here](https://github.com/tensorflow/tensorboard/blob/f801ebf1f9fbfe2baee1ddd65714d0bccc640fb1/tensorboard/plugins/scalar/vz_line_chart/vz-line-chart.ts#L704). 

It's source code as follows

```C
private resmoothDataset(dataset: Plottable.Dataset) {
  let data = dataset.data();
  const smoothingWeight = this.smoothingWeight;
  let last = data.length > 0 ? data[0].scalar : NaN;
  data.forEach((d) => {
    if (!_.isFinite(last)) {
      d.smoothed = d.scalar;
    } else {
      // 1st-order IIR low-pass filter to attenuate the higher-
      // frequency components of the time-series.
      d.smoothed = last * smoothingWeight + (1 - smoothingWeight) * d.scalar;
    }
    last = d.smoothed;
  });
}
```

which can be rewrote in python as follows:

```Python
def smooth(scalars, weight):  # Weight between 0 and 1
    last = scalars[0]  # First value in the plot (first timestep)
    smoothed = list()
    for point in scalars:
        smoothed_val = last * weight + (1 - weight) * point  # Calculate smoothed value
        smoothed.append(smoothed_val)                        # Save it
        last = smoothed_val                                  # Anchor the last smoothed value

    return smoothed
```

It's a recursive function and we summarized its formula below,

$$
\left\{\begin{matrix}
f(0) &=& data[0] \\
f(t) &=& f(t-1)*w + (1-w)*data[t]
\end{matrix}
$$

where $$data$$ is our original data, $$t$$ is the iteration steps, and $$w$$ is the smooth weigths which is shown as a scroll widgets in tensorboard.

