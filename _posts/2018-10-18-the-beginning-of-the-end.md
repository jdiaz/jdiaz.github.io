---
layout: post
title: "Inflection point for Java?"
date: 2018-10-18
---

If you were eager to try Java SE 11 and went to download the [official JDK](https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html), then you were greeted with an curve ball message.

![license](../../../assets/oraclelicense.png){:class="img-responsive"} 

The message reads something along the lines of: 'Heads up we changed our license, read it'. Upon reading you'll notice several changes, but the most outstanding one is:

Exerpt:
*
Further, You may not:
-    use the Programs for any data processing or any commercial, production, or internal business purposes other than developing, testing, prototyping, and demonstrating your Application;
*

There it is, pay up if you want to use JDK 11 or greater on for your commercial systems. Thats right, the official JDK implementation by Oracle is now pay to use (commercially). If you don't want to participate in the endless commercial subscription model to run your system you must embrace the sometimes has been referred to as [not-production-ready in the past](https://stackoverflow.com/questions/9344243/openjdk-ready-for-production), the [OpenJDK](https://openjdk.java.net/). 

![OpenJDK](../../../assets/openjdk_banner.png){:class="img-responsive"}

Granted, its possible to run your system on the OpenJDK, but it could require some carefuly testing and porting over any dependencies.

This is a bold move from Oracle, one that in my opinion could lead to a loss in market share for the Java programming language. At first glance the market share for Java seems [pretty strong](https://www.tiobe.com/tiobe-index/) on the Tobie index. Redmonk ranks it [second next to JS](http://sogrady-media.redmonk.com/sogrady/files/2018/08/lang.rank_.618-1.png). These indexes track things like [Google searches, Github projects and Youtube videos](https://en.wikipedia.org/wiki/TIOBE_index). The signs all point to Java remaning strong. However, I argue we are at a turning point in that dominance. Why? Let's look at developer happyness. How happy are developers using programming languages. Stack overflow annually polls developers actually using progamming languges and publishes the results. Python tops the most [loved of them all](https://insights.stackoverflow.com/survey/2018/#most-popular-technologies) and Java polls at a 45%. Now lets look at the [most dreaded](https://insights.stackoverflow.com/survey/2018/#most-loved-dreaded-and-wanted), Java polls at 49%. Programmers seems to dread Java more than they love it. There could be [many reasons for those results](). I would argue that, the combination of Java being dreaded by 50% of devs and businesses having to pay for commercial use, will kickoff the exodous away from the JVM. If you've everntried to get your boss to let you use that shinny open source technology you wanted, now is the time you will probably be heard.

Of course, migration will take place at a slow pace. Only time will tell if this is just another #JavaIsDead article or a billion dollar prediction. Time will tell.

![javaguy](../../../assets/openjavaguy.png){:class="img-responsive"}
