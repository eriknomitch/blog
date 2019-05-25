---
title: "Bufferbloat"
date: 2019-05-21T02:08:36-05:00
draft: false
tags:
  - "optimization"
  - "internet"
categories:
  - "guide"
---

## What is bufferbloat?

If your router sends **too much data** to your modem, your modem will "buffer" that data. The buffered data is now quite literally waiting in your modem until it can send it.

## Why do I care?

This wait period can be remarkably substantial and sporadic.

If you are affected by bufferbloat, you will have **perceivable spikes in lag**.


![Bufferbloat Diagram](/images/bufferbloat-diagram.jpg)

*Note:* Even if you have an "all-in-one" modem/router you can still have bufferbloat.

## Okay, do I have bufferbloat?

[DSLReports](http://www.dslreports.com/speedtest) and [SourceForge](https://sourceforge.net/speedtest/) have speed tests which also test bufferbloat.

If you are graded an `A+` or `A` your bufferblow is quite low and can probably stop reading this.

## My score is low. How do I fix it?

On your router's administration page, look for `QoS` or check if your router supports `QoS`.

### I have QoS

Great. Talk to me. [Section in progress...]

### I don't have QoS

You need a router that has QoS. I suggest one with [DD-WRT](https://dd-wrt.com/).

## I'm stuck.

Talk to me.

## Resources

* [Bufferbloat.net](https://www.bufferbloat.net)
* [Bufferbloat.net / Tests](https://www.bufferbloat.net/projects/bloat/wiki/Tests_for_Bufferbloat/)
* [untangle / Bufferbloat](https://wiki.untangle.com/index.php/Bufferbloat)

