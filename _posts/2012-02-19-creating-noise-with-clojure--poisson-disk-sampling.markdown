---
layout: default
title: Creating Noise with Clojure - Poisson Disk Sampling
---

Noise with Clojure via Poisson Disk Sampling
--

I recently had need of a random grid of more or less evenly
distributed points; simultaneously I've been looking for any excuse to
play with Clojure. To both these ends I've put together a quick
write-up of the Poisson Disk Sampling algorthim in what I hope will
contribute to the universe of idomatic clojure code.

Poisson Disk Sampling is often used to generate tightly packed points
that still maintain a minimum distance from one another. Applications
include texture supersampling or placing trees in a game. It appeals
to me as a simple algorithm to implement in a new language because
it's easy to visually verify things are working as expected, it it has
some minimal state to keep track of.

First let's demonstrate why generating 200 points with random x and y
values doesn't get us what we want. The following leverages
[seesaw](https://github.com/daveray/seesaw) to generate 100 randomly
distributed points.

{% highlight clojure %}

(use 'seesaw.core 'seesaw.graphics)
(def image (buffered-image 768 240))
;; list of random points inside bounds
(def random-points
  (take 200 
        (repeatedly 
         #(list (rand-int (.getWidth image)) 
                (rand-int (.getHeight image))))))
(def g (.getGraphics image))
;; draw each point as a circle on image
(doseq [point random-points]
  (draw g
        (circle (first point) (second point) 2 )
        (style :background "#FF0000")))
;; create a frame and give it a title and add image
(-> (frame :title "200 Random Points", 
           :content (label :icon image)
           :on-close :exit)
    pack! show!)

{% endhighlight %}

Results in a scattering of dots similar to this. Notice that while
random, this is not evenly distributed, and if each dot was a tree
we'd have a forest with some large bare spots.

![200 Random Dots](/img/posts/2012-02-19-creating-noise-with-clojure--poisson-disk-sampling/200-random-dots.png)

Poisson Disc Sampling generates points such that no point is closer
than distance _r_ from each other. First it generates a random point,
and from there generate a series of points around that point, discarding
any that fall close, less than _r_, to an exisiting point, then repeat.

To ensure fast lookups a grid is created and used to constrain the
number of comparisons it will take to ensure _r_ is maintained.

More specifically:
    
 1) Start with a random point within the bounding recatangle

 2) Generate k new points from that point, rejecting any who fall
    within min-distance of an existing point. 
