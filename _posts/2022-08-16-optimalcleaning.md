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

## The Math

Warning: this section contains math. It is for people who are curious about how I came up with the expected profit values. Reading this section will not improve your gameplay. It may, however, teach you something new about statistics! 

#### Binomial Distribution

In a situation where $$n$$ events with probability $$p$$ can only have two outcomes, success or failure, the probability of having $$x$$ successes follows a Binomial Distribution. Don't worry if you don't know what this means! Just understand that it is a way of representing the probabilities of each number of successes. A binomial distribution can be represented by the equation below.

$$ f(x) = {n \choose x} p^x(1-p)^{(n-x)} $$ where $$x = 0,1,2,...,n $$

Let's think about how we can apply this to cleaning. Let's say that we put 1,000 sauce on an egg. Let's consider a 'success' to be getting one or more 1,000 eggs. To find the probability of getting exactly 1 1,000 egg, we can use the formula above. The probability of a success is $$p=0.001$$, 1 in 1,000. The number of trials (taps) we will be simulating is $$n=1,000$$. We want to know the chance of getting $$x=1$$ success.  

$$\begin{eqnarray} {1000 \choose 1} 0.001^1(1-0.001)^{(1000-1)}\\= 1000 * 0.001 * 0.368 = 0.368 \end{eqnarray}$$ 

So the probability of exactly one success is 0.368! But this is not exactly what we want. We wanted the probability of getting 1 *or more* successes. In cleaning, if we get 2 of an egg, it still gives us one of them, so we do not want to just throw away those chances! To compute this, let's use a little trick.
We will compute the probability of getting exactly 0 successes. 

$$\begin{eqnarray} {1000 \choose 0} 0.001^0(1-0.001)^{(1000-0)} \\
= 1 * 0.1 * 0.368 = 0.3676 \end{eqnarray}$$ 

The probability of one or more successes accounts for every number 1 and larger. The probability of getting 0 successes is the only thing not accounted for. Therefore, the probaility of getting 0 1,000 eggs from 1,000 sauce + the probability of getting 1 or more 1,000 eggs from 1,000 sauce = 1. So to find the probability of getting 1 or more 1,000 eggs, we can do 1 - the probability of getting 0 1,000 eggs.

$$1 - 0.3676 = 0.6324$$

In other words, we have a 63.24% chance of getting a 1,000 egg given we use 1,000 luck sauce. This same probably applies to any egg given you use its amount of sauce. So getting a 1m egg using 1m sauce is 63.24%. 

#### Expected Profit

This was a bit of math, and if you don't understand what I just went through, don't worry! The main point is now we have a way to calculate the probability of getting a certain rarity egg given a certain sauce amount. To calculate the expected profit for a sauce amount, we can multiply this probability by the amount of money we would get from getting that egg! 

Consider this example where a 1 in 1,000 egg is the only egg possible (we either get it or get nothing). The expected return would then be $$0.6324 * \$1250 = \$790.5$$. However, we have to consider the fact that we spent $1,200 to add the luck sauce. So our profit is $$\$790.5 - \$1200 = -\$409.5$$.

In this case, we assumed that the only egg possible was a 1,000 egg. However, that is clearly not true for One in a Trillion. We have many different possible raritites. Additionally, we keep the highest rarity found. The formula for expected profit is therefore: the probability of getting a 1 trillion using the sauce amount\*the value of a 1 trillion + the probability of not getting a 1 trillion \* the probability of getting a 100 billion\*the value of getting a 100 billion and so on.

Where each probability is the respective binomial CDF for getting 1+ of that rarity. This could be written out as a full formula but there would be a large number of nested multiplications. This would be extremely error prone. To ensure I did not make a mistake, I wrote the following R function to calculate the expected profit of a sauce value.  

<div style='display:flex;justify-content:center;'>
<div class='table-wrapper' markdown='block'>

{% highlight R %}
f <- function(x) {
  tril <- 1 - pbinom(0,size=x,prob=1e-12)
  bil100 <- 1 - pbinom(0,size=x,prob=1e-11)
  bil10 <- 1 - pbinom(0,size=x,prob=1e-10)
  bil <- 1 - pbinom(0,size=x,prob=1e-9)
  mil100 <- 1 - pbinom(0,size=x,prob=1e-8)
  mil10 <- 1 - pbinom(0,size=x,prob=1e-7)
  mil5 <- 1 - pbinom(0,size=x,prob=1/5000000)
  mil <- 1 - pbinom(0,size=x,prob=1e-6)
  k750 <- 1 - pbinom(0,size=x,prob=1/750000)
  k500 <- 1 - pbinom(0,size=x,prob=1/500000)
  k250 <- 1 - pbinom(0,size=x,prob=1/250000)
  k100 <- 1 - pbinom(0,size=x,prob=1/100000)
  k75 <- 1 - pbinom(0,size=x,prob=1/75000)
  k50 <- 1 - pbinom(0,size=x,prob=1/50000)
  k25 <- 1 - pbinom(0,size=x,prob=1/25000)
  k10 <- 1 - pbinom(0,size=x,prob=1/10000)
  k5 <- 1 - pbinom(0,size=x,prob=1/5000)
  k2 <- 1 - pbinom(0,size=x,prob=1/2000)
  k <- 1 - pbinom(0,size=x,prob=1/1000)
  o500 <- 1 - pbinom(0,size=x,prob=1/500)
  
  vals <- list(
    c(tril,   400000000000),
    c(bil100, 50000000000),
    c(bil10,  6000000000),
    c(bil,    700000000),
    c(mil100, 80000000),
    c(mil10,  9000000),
    c(mil5,   4500000),
    c(mil,    1000000),
    c(k750,   750000),
    c(k500,   500000),
    c(k250,   250000),
    c(k100,   100000),
    c(k75,    90000),
    c(k50,    60000),
    c(k25,    30000),
    c(k10,    12000),
    c(k5,     6250),
    c(k2,     2500),
    c(k,      1250),
    c(o500,   750)
  )
  
  profit <- 0
  
  for (i in c(1 : length(vals))) {
    
    currProfit <- vals[[i]][[1]]*vals[[i]][[2]]
      
      for (j in i:1) {
          
        if (j != i) {
          currProfit <- currProfit * (1-vals[[j]][[1]])
        }
        
      }
    
    profit <- profit + currProfit
    
  }
  
  return(profit - (1.2*x))
}
{% endhighlight %}

</div>
</div>

Feel free to run $$f(sauce)$$ if you have R to see what the expected profit of a sauce value is! I plan on putting this as a calculator on the site too. :)

Thanks for reading!