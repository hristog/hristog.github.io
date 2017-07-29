
# Energy conversion efficiency
From [Wikipedia][ece_wiki]:
> Energy conversion efficiency (_η_) is the ratio between the useful output of an energy conversion machine and the input, in energy terms. The input, as well as the useful output may be electric power, mechanical work, light (radiation), or heat.

Welcome to another post from my [Fantasy Football][fepl_section] team selection [series][fepl_selection_series]. Today, we're going to view football players as playing-time "conversion machines", and thus aim to draw a suitable parallel to the _energy conversion efficiency_ metric, for the purpose of gathering a different dimension of insights about the Fantasy Premier League transfer market.

# Playing time

Particularly, for completion of the analogy, and actually for enabling our analysis to provide meaningful conclusions, we'll imagine - within the context of this post only - that football players are machines
that convert playing minutes into fantasy football points.

Since the average number of points per match[^playing_only] an FPL player scored in 2016/2017 was only 2.97, our ratio of interest will be _average number of points scored per 90 minutes_ (which is the duration of the regular time of all English Premier League matches). This means that we'll be looking for players who were able to take as many as possible playing minutes as input, and produce as many as possible points as output, namely footballers with high _playing time conversion efficiency_.

[^playing_only]: This statistic, naturally, considers only those matches in which a player participated for at least a single minute. Averaging over playing and non-playing "participations" brings us down to an 1.31 average points scored per match, across the entire last season.

There's a gotcha involved, of course, and - as you may have guessed already - assuming the aforementioned ratio to be the only criterion employed, when drawing conclusions regarding playing efficiency, would be an utter failure at best.

Consider, for instance, an imaginary footballer who scores two goals in the first game of the season, then gets an injury which prevents him from playing a full-match for 10 weeks, then scores a goal and makes an assist in his second match of the season, then gets injured again, until the very last match of the season, when he comes in for about 35 minutes, as a substitute - no goals, no assist this time. What do you think? Would it have been reasonable, in hindsight, to have purchased this player in the beginning of the season and to have kept him in your squad until the very end of the season, without having transferred him out. I believe your answer is No, and it should be - despite the high _playing time conversion efficiency_ ratio he managed to squeeze out. Perhaps, he's an extremely skilled footballer, but we have to keep in mind his injury proneness as well, as I alluded to in the [first post][team_play_contributions_fwds] of my team-play contributions [series][team_play_contributions_series]. The number of playing minutes can usually be the best obtainable proxy, as all datasets, involving physiological player data, are strictly proprietary.

Therefore, as an outlier detection method, we'll employ the following simple heuristic: we'll filter out all players,
who participated in less than a pre-defined portion of all matches of their team; I've opted for 75%[^participation_threshold],
which seems to be a reasonable enough figure[^fa_participation_requirement]. This, basically, means that we'll be only focusing on players who took part in at least 29 Premier League games during the 2016/2017 season.

[^participation_threshold]: The straightforward maths goes as follows: 75% x 38 = 28.5, and to be on the strict side, I've taken the ceiling of that number, namely 29, to be the minimum requirement for a number of matches played, in order to be included into our analysis.

[^fa_participation_requirement]: The flat requirement, for granting permissions to non-EU players to obtain work permits and join English football clubs officially, used to be international-level participation of exactly 75% or more, over the past 24 months. But, in 2015, the requirements were re-assessed and subsequently updated to include tiers, based on the FIFA ranking of the particular non-EU country, whose passport is held by the footballer in question. Nevertheless, for the lowest ranking range, it is still required that the participation ratio, on international level, is [at least 75%][footballer_work_permits] for potential new signings.

# Visualisation

<a href="/uploads/fepl_playing_time_conversion_efficiency/Playing_time_converstion_efficiency.png" target="_blank"><img src="uploads/fepl_playing_time_conversion_efficiency/Playing_time_converstion_efficiency_230x256.png" alt="Playing Time Conversion Efficiency (FPL Season 2016/2017)"></a>

This time we've got one graph only - nevertheless, it's fully-packed with useful information (that's why it doesn't need any companions). Firstly, we've got a bunch of points on the 2-D plane - each one of them
corresponds to a player, who played in at least 29 English Premier League matches in 2016/2017[^fpl_only].

[^fpl_only]: Namely, in the context of the Fantasy Premier League 2016/2017 selection pool, that's 164 players, out of 683 in total. It is noteworthy to mention Zlatan Ibrahimovic who, among others, didn't make the cut to be included into our conversion efficiency analysis, as he only played in 28 of Manchester United's Premier Leagues games.

Along the _x_-axis, there is the total points count for each of the players, and along the _y_-axis - the average number of points scored per 90 mins (that is, essentially, our _playing time conversion efficiency_ ratio), both of which will serve, visually, for comparative purposes. A further dimension that has been depicted is the average player value, encoded as the area[^circle_area] (or size, in layman terms) of the corresponding circle. Thus, the total points and conversion efficiency readings, should be taken based on the centre of a player's circle. I've further annotated the most important quadrant - the upper right one, where we have the highest total points totals and the highest time conversion ratio - with the footballer names, for clarity (although, to be fair, this wasn't really necessary for Agüero or Sánchez, due to the enormous transfer value of the former, and the top rank - in total points terms - of the latter). Last but not least, I've colour-coded the footballer circles based on their playing line, in order to be
able to visually distinguish patterns, related to individual lines.

[^circle_area]: In fact, for the purpose of facilitating visualisation clarity, I have exponentiated - by a constant - all player average values, in order to put further emphasis on the relative differences. Thus, please, note that the circle areas (or radii) do not correspond to the average values for the FPL 2016/2017 season, in a one-to-one fashion.

A few quick observations:

- No goalkeeper has managed to score more than 150 points.
- The average transfer values of goalkeepers and defenders are lowest, whilst midfielders cost higher on average, and forwards cost even higher. This is not that surprising, given the fact that the playing lines of the highest-point-scoring footballers are exactly the latter two.
- Despite the leadership of the forwards - in the value ranking - we can clearly see that, in terms of scoring fantasy football points, the best-performing midfielders are at least as good, and as efficient, as the best-performing forwards.

Finally, as an example of the usefulness of the graph, let's consider the following players, for the purpose of performing some straightforward head-to-head comparisons:

- Gary Cahill (DEF)
- Marcos Alonso (DEF)
- Gylfi Sigurdsson (MID)
- Joshua King (MID)
- Bamidele Alli (MID)
- Roberto Firmino (MID)
- Diego Da Silva Costa (FWD)
- Romelu Lukaku (FWD)

It is obvious that one would have been better off with a combination of King and Cahill, instead of Alonso and Sigurdsson. Further, Alli ranks much better - whilst characterised by similar average value - than Firmino, and one would have had a more successful selection, if it had included Lukaku, at the expense of Costa.

# Conclusion

This marks the end of the current analysis, concerned with playing time conversion efficiency. If you
have found this post useful, please, feel free to share a link to it on your social media profiles.
Ciao until [next time][fepl_selection_series] ;)

[ece_wiki]: https://en.wikipedia.org/wiki/Energy_conversion_efficiency
[fepl_selection_series]: /tagged/fpl-selection
[fepl_section]: /tagged/fantasy-football
[team_play_contributions_series]: /tagged/team-play-contributions
[team_play_contributions_fwds]: /team_play_contributions_of_the_top_forwards_for_the_fpl_season_2016_2017.html
[footballer_work_permits]: http://www.inbrief.co.uk/football-law/footballer-work-permits/


---

