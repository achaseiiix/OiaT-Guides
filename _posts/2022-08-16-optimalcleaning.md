---
layout: post
title: Optimal Cleaning
permalink: /optimal-cleaning-guide/
image: "images\\cleaning-profit-guide.jpg"
description: Learn how to make the most money from cleaning!
type: guide
author: achaseiiix
---

## Introduction

This guide will teach you how to clean optimally. It details how to make the most money from cleaning possible. If you are not familiar with cleaning or how it can make money, please check out this **[Introduction to Cleaning Guide]({% post_url 2022-09-16-intro-cleaning %})** I wrote. It is important to note that all of this is based off of math that I programmed a computer to calculate. It is likely that it is off by a small degree due to numerical precision and potential human error, but I am confident that the principles will hold nonetheless.

## Sauce Thresholds

If you don't care to play completely optimally and just want an idea on what to do, here are some sauce thresholds you can clean with. These are somewhat arbitrary and are based off the fact that you *probably* won't get unlucky enough to drop down to the threshold below.

<div style='display:flex;justify-content:center;'>
<div class='table-wrapper' markdown='block'>

| Wallet Size | 'Safe' Luck Sauce | Expected Profit per Egg |
|-----------|-------------------|-------------------------|
| <$500m      | -                 | -                       |
| $500m       | 2.5m              | $8.2m                   |
| $1b         | 5m                | $14m                    |
| $5b         | 25m               | $48.5m                  |
| $10b        | 50m               | $83.7m                  |
| $25b        | 125m              | $170m                   |
| $50b        | 250m              | $279m                   |
| $100b       | 500m              | $446m                   |
| $250b       | 1b                | $684m                   |
| $500b       | 2b                | $945m                   |
| >$1t        | 3.95b             | $1.08b                  |

</div>
</div>

## Getting into the Details

If you want to know more about why I have chosen those sauce thresholds, first consider the graph below.

{% include profits.html %}

As can be seen, the expected profit per clean steadily increases as you put more sauce into an egg. It peaks at around **3.95b sauce**, the sauce value with the maximum expected profit. Any value above that is still profitable, but less so than 3.95b. The main takeaway here is that there **are no magic numbers**. 

It may seem intuitive to say something like "7m sauce per egg will be more profitable than 10m sauce per egg because it is close to 10m but 10m is far from its next upgrade, 100m." This is *incorrect*. The graph clearly shows a smooth increase in profits. There is no drop at a value like 10m. This is because the profits come from the larger eggs! A 10m egg has a better chance of getting a 100m egg than a 7m egg does, and that's really where you will make the most money!

In other words, no sauce values (until 3.95b) should be avoided. **If you want to make the most money, constantly increase or decrease the amount of sauce you put into your dirty eggs depending on the size of your wallet.** I have demonstrated one example of this in the threshold table above. I suggest to put sauce of about **1/200** of your wallet most of the time. This is definitely an arbitrary choice. It is just a bet amount that I personally consider to be *safe enough* to suggest to a reader without a high risk of disappointing them with bankrupt. If you are feeling more risky, go for maybe 1/100 of your wallet on each egg at the beginning of a dirty egg cleaning session.

There does exist a luck sauce at each wallet level that will be enough to not go bankrupt, and it is probably higher than some of the values I have suggested in the table. However, these values are currently unknown. It is a complicated problem to solve, but we are working on it.