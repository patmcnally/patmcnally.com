---
layout: default
title: Projects Index
---

Projects
========

For all the hours spent hammering away at the keyboard, I've managed
to accomplish a few minor things. These are some select projects I've
either been responsible for or a major contributor too.

I build primarily on the Unix stack, and my framework of choice is [Ruby on
Rails](http://rubyonrails.org/). Meanwhile [Node.js](http://nodejs.org) is
becoming an attractive way to do really cool things very fast. In my past life
I dabbled in spacecraft design and robotics development. Most notably as the
project manager and lead developer on Washington University's Akoya
nanosattellite, then some time in graduate school interfacing between custom academic mobile robots and [Player/Stage](http://playerstage.sourceforge.net).

UpprDwnr
--------

![UpprDwnr Screenshot](/img/work/uppr_dwnr.jpg)

UpprDwnr was an effort to short-cut sentiment analysis on Twitter by
encouraging the use of two distinct hashtags: #uppr and #dwnr. A
node.js process was connected to the Twitter feed,
constantly on the look out for those two tags. Once one was found we
used a simple heuristic to parse out the user, url, or other hashtag
that was receiving the positive or negative sentiment.

I built the process that consumed incoming tweets, written initially in Erlang and
later in node.js.  I also did some heavy lifting on the application powering
the public-facing website. We spent a lot of time trying to
encourage the use of the hashtags, but they never took off. In the end we had
a system designed for orders of magnitude more people than were using it.
Lesson learned, don't overbuild until you know you're onto something.

Built with [@stubelshe](http://twitter.com/stubelshe) and [@jaredmacke](http://twitter.com/jaredmacke)

Reaper
------

![Reaper Collage](/img/work/reaper.png)

Reaper is the informal name for an internal system built by Brighton to automate
the work flow around low volume tightly targeted communications on multiple channels. The client
was a large agricultural company that every fall had large numbers of real world harvest reports they
wanted to communicate to a very targeted audience, audiences on the scale of one or two counties.

This current harvest, a hundred user accounts were involved in processing over five thousand individual plot reports. Each plot report
was transformed into email messages, direct mailing postcards, SMS messages, data feeds for multiple websites and third
party web based maps. The reports were automatically checked for errors, populated into
templates depending on brand, crop, messaging type, or growing conditions of the targeted audience. Each communication was
proofed and approved by internal editors, client side technical experts, and client side marketing team members. Once approved
the appropriate vendors were notified and requested to log in and retrieve the necessary pdfs or mailing lists. Automatic services
were also dispatched, such as SMS publication, or updating a map on a third party map.

The current iteration of the system is a Ruby on Rails application designed and built by myself along with a team of developers and
digital producers over the last two years.

Built at the verdant [Brighton Agency][brighton]{:class='brighton-link'}.

SeeBeyondtheBag.com
-------------------

![SeeBeyondTheBag.com Image Mosaic](/img/work/see_beyond_the_bag.png)

[SeeBeyondTheBag.com](seebeyondthebag.com) is a microsite for the Natura family
of pet food brands. Natura prides itself on selecting top quality ingredients from
only the best suppliers. From raw supplier data we built an interactive experience
walking the visitor from bag to ingredient source displayed on a map.

Built in PHP on-top of a custom CMS that utilizes much of the [MapBox](http://mapbox.com) tool chain.
Inspired by systems like [Jekyll](https://github.com/mojombo/jekyll/wiki) the CMS generates a static
site suitable for hosting anywhere inside Procter & Gamble's infrastructure.

The PHP application backing SeeBeyondTheBag.com also outputs static single page applications custom built for
two national brand pet retailers. These single page apps are iframed in on the Innova microsite found on both  [PetSmart](http://pets.petsmart.com/brands/innova/innova-ingredient-sources.shtml)
and [PetCO](http://www.petco.com/petco_page_pc_innovasources.aspx). This integration has made us thankful
we're generating a static site, allowing us to easily scale with the demands of these retailer's sites.

Built at the ingenious [Brighton Agency][brighton]{:class='brighton-link'}.

Scottrade Hadoop Cluster
------------------------

![Hadoop Mascot](/img/work/hadoop.jpg)

Scottrade was receiving more information from it's add placements than
it could handle. In an attempt to wring some buisness data from the
terrabytes of log files I built a Hadoop Cluster than could be
summoned from Amazon's Web Services. The cluster would gather, do
rudimentary interpretation and translation, and store the data in a
large HFS running on-top of Amazon's EBS. We had just begin to return
results when Scottrade switched ad-serving platforms and began
receiving better statistics directly from their vendor.

Built at the convivial [Brighton Agency][brighton]{:class='brighton-link'}.

Growing Knowldege
-----------------

![CottonCommunity Screenshot](/img/work/growingknowledge.png)

The Growing Knowledge Newsletter, Agronomic Update, and Agronomic
Alerts are read by hundreds of farmers a day. These communications are
tailor made at the county level, giving farmers pertinent information
and letting them know of any disease or pests affecting their
area. Getting these communications in the inboxes of farmers was
proving to be a very time intesive process. We built a web application
that integrates with [ExactTarget](http://www.exacttarget.com). This application takes the
pain out of sending a large number of emails to very precisely targeted geographic groups.

Built at the vivacious [Brighton Agency][brighton]{:class='brighton-link'}.

Cotton Community
--------

![CottonCommunity Screenshot](/img/work/cottoncommunity.jpg)

CottonCommunity was a social network for cotton farmers, particularly
cotton farmers who grew Deltapine brand cotton. It also became the hub
for submitting and viewing yield data for growers working with
experimental varieties. Learned alot about building a big complicated
system in Rails, mostly by doing it the wrong way first. Eventually it
ran solid for the greater part of 3 years before it was put to
pasture. I learned even more about when you should be saying no, like
maybe from the very beginning.

Built at the indefatigable [Brighton Agency][brighton]{:class='brighton-link'}.

Family
----------

![Family Screenshot](/img/work/family2.jpg)

Yup, I'm that guy, I just put my family as the last item in my list of
projects. If I kept track of sleepless nights per project, this would
definitly have the most.

Built with the beautiful Stephanie.

[brighton]: http://www.brightonagency.com 'Brighton Agency'
