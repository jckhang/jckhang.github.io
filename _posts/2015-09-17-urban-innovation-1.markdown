---
layout: post
title: "Urban Innovation #1"
modified:
categories: 
excerpt: This is the first week assignment of CUSP Civic Anlytics and Urban Intelligence class
tags: [CUSP]
image:
  feature:
date: 2015-09-17T10:46:59-04:00
---
{% include _toc.html %}

#Approaching NYC No-Cabs-At-4PM Problem 

No-Cabs-At-4PM is an age-old NYC problem. It’s some time after 4PM and you step out to look for a cab. You giggle as you watch a tourist repeatedly try and hail cabs with the off-duty lights on, but then you realize the joke is on you too. Most of the cabs have off-duty lights on. Better luck next time.

Social Data Scientist, [Ben Wellington](https://about.me/benwellington) tries to using taxi data to prove this myth and finding out how to fix this problem. Ben Wellington wants to look inside the NYC Taxi Revenue data and try to find out and fix the problem. Ben uses the [2013 NYC Tax Trip Open Data FOILed (aka Freedom of Information Law)](http://chriswhong.com/open-data/foil_nyc_taxi/) by Chris Whong. He plotted the trip data and found a dreaded decrease in average revenue per minutes during 2:50PM and 6:10 PM, and reaches a low point at 4:30 PM. 

<figure>
	<img src="/images/average_revenue.png">
	<figcaption>Figure 1: Hourly Average Revenue</figcaption>
</figure> 

To explain why drivers choose to do a shift change during the period of time with highest demand and potential revenue, Ben gave his answer. 5:08AM/PM is the best time to split revenue between two drivers so they each got roughly equal pay for a 12 hours shift. See Figure 2. He also gave one solution to move the best time of shift change forward to 3AM/PM. That was a $2.5 surcharge from 3AM to 3PM and a $-1.5 surcharge between 3PM to 3AM for each ride. See Figure 3.

<figure>
	<img src="/images/12_hour_revenue.png">
	<figcaption>Figure 2: 12 Hour Revenue</figcaption>
</figure>	


<figure>
	<img src="/images/12_hour_revenue_with_surcharge.png">
	<figcaption>Figure 3: 12 Hour Revenue with surcharge</figcaption>
</figure>

Ben's model is just simple as it seems. It's easy to duplicate. But the data was outdated, and as Uber cars' addition to the market, their impact on the hourly revenue can not be neglected. The new data and new model should be tested. The TLC has released the data of 2014 and 2015 Yellow and Green Taxi Trip data early at August. This should credit to the work that Ben, Chris and others who insist in 'Open Data Movement'.
