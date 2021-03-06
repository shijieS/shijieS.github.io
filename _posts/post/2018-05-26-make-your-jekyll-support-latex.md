---
date: '2018-05-26 04:27 +0800'
published: true
layout: post
categories:
  - tools
tags:
  - tools
comments: '1'
---
Cool Example: $$ x^2 + y^2 = \frac{z^3}{\mathcal{E}_{\delta}}$$

If you want to solve the problem immediately, just go to [this link](https://github.com/github/pages-gem/issues/307).

Or, reading on 

I want to make my jekyll surpport latex math. I tried many ways, such as the following link:
- [Writing Math Equations on Octopress](http://www.idryman.org/blog/2012/03/10/writing-math-equations-on-octopress/)
- [How to use mathjax in Jekyll?](How to use mathjax in Jekyll?)
- [Math Engine Mathjax](https://kramdown.gettalong.org/math_engine/mathjax.html)
- [How to use LaTex in Markdown](http://flennerhag.com/2017-01-14-latex/)
- [Math block](https://kramdown.gettalong.org/syntax.html#math-blocks)

I just cannot figure out, where to put these codes, even from the jekyll official way [Math support](https://jekyllrb.com/docs/extras/#math-support). Besides I am also little worried about the outdated way.

two things are sure:
- In '_config.xml' file,  I should use kramdown engine
{% highlight json %}
markdown: kramdown
{% endhighlight %}

- The following code should be used
{% highlight html %}
<script type="text/x-mathjax-config"> MathJax.Hub.Config({ TeX: { equationNumbers: { autoNumber: "all" } } }); </script>
  <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      tex2jax: {
        inlineMath: [ ['$','$'], ["\\(","\\)"] ],
        processEscapes: true
      }
    });
  </script>
  <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
{% endhighlight %}

Finally, I found this [this link](https://github.com/github/pages-gem/issues/307), went to his/her repostory and got the idear of position to put these codes.

I should put these codes in the all-shared layout file which is '_include/head.html', see this file code as following

{% highlight html %}
<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>
    </title>
    <link rel="shortcut icon" type="image/x-icon" href="{{site.baseurl}}/assets/res/logo-half.png">
    <link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/materialize/0.99.0/css/materialize.min.css">
    <link rel="stylesheet" href="//fonts.googleapis.com/icon?family=Material+Icons">
    <link rel="stylesheet" href="{{site.baseurl}}/assets/css/main.css">
  	<!-- mathjax code should add here -->
    </script> -->
    <script type="text/x-mathjax-config"> MathJax.Hub.Config({ TeX: { equationNumbers: { autoNumber: "all" } } }); </script>
    <script type="text/x-mathjax-config">
      MathJax.Hub.Config({
        tex2jax: {
          inlineMath: [ ['$','$'], ["\\(","\\)"] ],
          processEscapes: true
        }
      });
    </script>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
  </head>
</html>
{% endhighlight %}
