---
  layout: post
  title: "Generic Skip List (map) in Java"
  categories: projects
---

The skip list is a interesting probabilistic data structure which can be used as an alternative to trees. Below is a simple implementation in Java using generics to store key-value pairs and therefore works as a map.

Code available on my [GitHub page](https://github.com/AntonFagerberg/SkipList-Map-Java).

{% highlight java %}
{% github_sample /AntonFagerberg/SkipList-Map-Java/master/src/SkipList.java %}
{% endhighlight %}

{% highlight java %}
{% github_sample /AntonFagerberg/SkipList-Map-Java/blob/master/src/QuadNode.java %}
{% endhighlight %}
