---
layout: post
title: Stephen Curry is a Black Swan - A once in a 151-year season
categories:
- blog
---

There will be two epoch's in the history of the NBA, before Curry, BC, and after Curry, AC; Fivethirtyeight's "[Stephen Curry is the Revolution](http://fivethirtyeight.com/features/stephen-curry-is-the-revolution/)" and  "[How the Golden State Warriors are Breaking the NBA](http://fivethirtyeight.com/features/how-the-golden-state-warriors-are-breaking-the-nba/)" are among recent articles arguing how absurdly good his 2015-2016 season has been. There is no hyperbole too grand. Is he a "[Golden God?](http://mashable.com/2015/12/04/steph-curry-wtf-omg/)"

![](/assets/images/Stephen-Curry-shooting-form.jpg){:style="float: right;margin-right: 7px;margin-top: 7px;"}
For the team's 21st win against the Raptors he scored 44 points on 14-24 shooting, 9-15 from three and had 7 assists! For almost any other player that would be considered a career game. His team is 21-0 this season. This team will probably break the all time wins record and point differential for a season.

From a statistical point of view there is no argument against him being the NBA MVP. There is no argument that his team will go down as one of the top three of all time. Most likely the best team ever. But what I will show is that he is having the greatest season of any player - ever - and it's not even close.

I also want to know how rare is this? And, if so, could, or should, we have seen this coming? In this post I will use a simple statistic, the standard deviation, to try and explain how special this season is for Stephen Curry.

## The PERfect Season

A common statistic used in basketball is a player's Player Efficiency Rating, or PER.

The [formula](https://en.wikipedia.org/wiki/Player_efficiency_rating) for PER is the reason everyone is afraid of math. Nonetheless, it is a go-to stat that gives a sense of how good a player is. Before this season the five highest PER's were:

<table class="stats_table" data-crop="50" data-freeze="6">
<tbody>
<tr class="">
<th class="align_right">Rank</th>
<th class="align_left">Player</th>
<th class="align_right">PER</th>
<th class="align_left">Season</th>
<th class="align_right">Team</th>
</tr>
<tr class="">
<td class="align_right">1.</td>
<td class=""><a href="http://www.basketball-reference.com/players/c/chambwi01.html">Wilt Chamberlain</a>*</td>
<td class="align_right">31.82</td>
<td>1962-63</td>
<td><a href="http://www.basketball-reference.com/teams/SFW/1963.html">SFW</a></td>
</tr>
<tr class="">
<td class="align_right">2.</td>
<td class=""><a href="http://www.basketball-reference.com/players/c/chambwi01.html">Wilt Chamberlain</a>*</td>
<td class="align_right">31.74</td>
<td>1961-62</td>
<td><a href="http://www.basketball-reference.com/teams/PHW/1962.html">PHW</a></td>
</tr>
<tr class="">
<td class="align_right">3.</td>
<td class=""><a href="http://www.basketball-reference.com/players/j/jordami01.html">Michael Jordan</a>*</td>
<td class="align_right">31.71</td>
<td>1987-88</td>
<td><a href="http://www.basketball-reference.com/teams/CHI/1988.html">CHI</a></td>
</tr>
<tr class="">
<td class="align_right">4.</td>
<td class="bold_text"><a href="http://www.basketball-reference.com/players/j/jamesle01.html">LeBron James</a></td>
<td class="align_right">31.67</td>
<td>2008-09</td>
<td><a href="http://www.basketball-reference.com/teams/CLE/2009.html">CLE</a></td>
</tr>
<tr class="hl">
<td class="align_right">5.</td>
<td class=""><a href="http://www.basketball-reference.com/players/j/jordami01.html">Michael Jordan</a>*</td>
<td class="align_right">31.63</td>
<td>1990-91</td>
<td><a href="http://www.basketball-reference.com/teams/CHI/1991.html">CHI</a></td>
</tr>
</tbody>
</table>

<p> </p>


This season Stephen Curry's PER is 35.36. The top five are separated by an average of 0.0475, or 4.75 parts in 100. Steph Curry is separated 3.54 from the top season, or about 75 times better than the previous differences. But this is just the beginning of the story.

## Measuring PER

Using data for all qualified players we can look a plot of every player's PER for the 2015-2016 season:

![](/assets/images/Curry_Normal.png)

Assuming that PER is distributed normally, we see Stephen Curry is far to the right in the distribution. How far? The PER data has the following descriptive statistics:
```
Number of Players: 321
Minimum PER: -1.160000
Maximum PER: 35.470000
Mean PER: 14.357009
Standard Deviation: 5.110888
Variance: 26.202807
Skew : 0.557577
Kurtosis: 0.933902
Number of Standard Deviations Stephen Curry is from the mean: 4.130983
```

Curry's PER is over 4 standard deviations from the mean! The picture to the right can help explain what this means. The graph shows the percentage of data under the distribution between multiples of the standard deviation. ![](/assets/images/Standard_deviation_diagram.svg){:style="float: right;margin-right: 7px;margin-top: 7px;"} For example, about 68.2% of the data is contained between -1 and 1 standard deviations from the mean. The standard deviation is denoted by σ. There is approximately 95% of the graph between ±2σ and roughly 99.7% between ±3σ. By the time we get to ±4σ about 0.999936% of data is realized. This means the expected frequency with which we would witness an event outside 4σ is 1 in 15787. This includes both the positive tail and the negative tail. Thus, the frequency on the positive end is 1 in 31574. The interpretation for the PER data is that Stephen Curry's current season will happen 1 time for every 31,574 statistical NBA seasons.

<blockquote>
If there are 350 qualified player seasons per year then Curry's 2015-2016 season will happen every one time for one player every 96 NBA seasons. And this is an underestimate. The true value ( 4.13σ) is once every 151 years.
</blockquote>

<p></p>

This season, if it continues, is beyond special. It may be a Black Swan event. From Wikipedia, A [Black Swan event](https://en.wikipedia.org/wiki/Black_swan_theory)

1. comes as a surprise,
2. has a major effect, and
3. is often inappropriately rationalized after the fact with the benefit of hindsight.

Right now the first of these has been realized. While his performance was expected to be great no one could predict it would have been historic. Will it have a major effect? This is yet to be seen but my feeling is it will; There may be rule changes to accommodate the rest of the league like changing the three-point line or changing the hand-check rule; teams will eventually implement "[Jordan rules](https://en.wikipedia.org/wiki/Jordan_Rules)" to stop him; and the way teams draft and retain player's will change based on his performance.

The last point is fun to think about. For example, [this GQ](http://www.gq.com/story/steph-curry-nba-best-player) story tries to explain Curry's greatness by claiming some practice methods he employs are "borrowed from the stuff that got the Apollo astronauts ready for the moon." [This article](http://www.basketballworkouttips.com/stephen-curry-shooting-form-secret/) simply states "the main component for his success is his consistent release." [Here](https://www.quora.com/What-makes-Stephen-Curry-such-a-good-basketball-player) is a Quora thread where his greatness is attributed to "having the most devastating pump fake in the history of the game," he "doesn't hesitate, which saves valuable fractions of a second," but most importantly, he "has the most heart," whatever that means.

What more can be said? If Curry's season ends as it has begun it will not simply be great. It will be something no one will see again until your great-great-great grandchildren's time. Thank goodness for YouTube.
