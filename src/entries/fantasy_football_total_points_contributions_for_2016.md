---
title: Fantasy Football Total Points Contributions for Season 2016/2017
publish_date: Jul 23th, 2017
tags:
  - fantasy-football
  - football
  - fpl
  - fpl-selection
  - analysis
---

# Fantasy Football
## The Underlying Idea
From [Wikipedia][fantasy_football_wiki]:
> Fantasy Football [is] a game in which participants assemble an imaginary team of real life footballers and score points based on those players' actual statistical performance or their perceived contribution on the field of play.

In other words, football aficionados make selections - subject to a pre-defined set of constraints (e.g., maximum number of players per team etc.) - which are a form of encoded predictions of how well a subset of the entire player pool will perform. Fantasy football managers usually enhance the selection process by following news outlets, and by performing statistical analyses of various degrees of complexity.

## The Fantasy Premier League
There's an entire [section][fepl_section] on this blog, dedicated to analysis of fantasy football competitions, and predominantly targeting the portion of fantasy managers, who are interested in supplementing their knowledge and insights by delving into statistically-supported articles.

In a [series][fepl_selection_series] of posts, focused on the [Fantasy Premier League][fepl_site], I'll attempt to assist you in improving selection (or verifying that it's already perfectly-polished!), or even create an initial one, based on statistical analysis or relatively simple heuristics. If you haven't created an account yet, it's probably a good idea to head over to the Fantasy Premier League's registration [page][fepl_register] and become a fantasy manager before the official start of the [season][epl_fixtures] (which is in the second week of August).

# Fantasy Season 2017/2018
## Player Selection
The game organizers have conveniently provided a printable single-page [reference][fepl_player_list] to the last season's performance (in terms of total number of points only, however) of the footballers which comprise the current transfer pool. One of the next posts, in my Fantasy Football [series][fepl_selection_series], is specifically concerned with scraping and parsing that list, and proposes an algorithm for finding optimal selections, using the minimal information provided as a starting point.

This post, however, will focus on a bit deeper and more interesting look at last season's total points - we'll see how each one of the top 50 players ranks relative to his team-mates, as well as players from opponent teams. In other words, this study will provide insights into a player's degree of contribution, with respect to the same positional line [^fepl_positions], as well as the entire squad.

[^fepl_positions]: In the Fantasy Premier League game, all players are divided into 4 categories of positions, which are fixed for the entire course of the season. Every player
can be assigned only one position from the following list: goalkeeper, defender, midfielder, and forward.

## Visualisations
<div class="img-box">
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_overall.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_overall_170x256.png" alt="Total Points (FEPL 2016/2017, whole season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_1h.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_1h_170x256.png" alt="Total Points (FEPL 2016/2017, first half of season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_2h.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_2h_170x256.png" alt="Total Points (FEPL 2016/2017, second half of season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_overall.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_overall_172x256.png" alt="Contribution to Team Total Points (FEPL 2016/2017, whole season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_1h.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_1h_172x256.png" alt="Contribution to Team Total Points (FEPL 2016/2017, first half of season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_2h.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_2h_172x256.png" alt="Contribution to Team Total Points (FEPL 2016/2017, second half of season)"></a>
</div>

The graphs presented here contain information regarding overall contributions, in terms of total number of points[^fepl_points]. The contributions are colour-coded, depending on  whether they represent player-only, line-only (i.e., the total point score of all goalkeepers, defenders, midfielders or forwards in a given team) or total team contributions. Particularly, the top 50, high-scoring, players are considered, and - in all graphs - the ordering of players is fixed, so that the highest scoring one is at the top, and the lowest scoring one - at the bottom, respectively.

Essentially, there are two sets of visualizations:
: absolute total number of points scored for each of the top 50 highest scoring players, their corresponding line, and their team total;
: relative number of points (in terms of percentage) that each player contributed to his playing line, along with the contribution of that line to the team total.

For the purpose of providing some sort of a temporal dimension, and a better idea as to how each individual player, line and team ranked as time went by, each of the two sets of plots is further subdivided into three categories (each alloted a dedicated bar chart): contribution across the entire 2016/2017 season, and in each half, separately.

Given this context, the graphs become more or less self-explanatory, enabling one to draw straightforward conclusions. We can clearly see the total domination of Sánchez (264 points), who was the winner of the season, with a remarkable performance in the midfield line of Arsenal, while neither of the latter were on the top 2 positions in their corresponding rankings (the respective scores were 1044 and 2015 points, for the Arsenal midfield line, and the team overall). The runner-up, Hazard (224 points), also demonstrated significant contribution in Chelsea's midfield line (952 points), which itself didn't rank nearly as high as those of Liverpool (1214 points) and Manchester City (1153 points).
While this study is not focused on player transfer values, it is imperative to point your attention towards Swansea's Sigurdsson, whose average value was only £7.42. Nevertheless, he managed to contribute by a rate higher than that of Sánchez to his corresponding midfield line, and managed to net 181 points in total - for reference, that was only 15 less
than Diego Costa from Chelsea. However, the average total value of the latter was £10.42, while that of Arsenal's Alexis Sánchez was even higher - £11.51.

Along an analogous chain of reasoning, we see a clear justification for Lukaku's [£75m transfer][lukaku_transfer] to Manchester United this summer. The forward finished at the top in his playing line (221 points), and his contributions were greater in proportion - 12.5% vs. 10% and 16.3% vs. 12.5% - relative to his runner-up, Harry Kane (220 points).
The latter, team-based comparison provides indication of Lukaku's significant contribution, from within a context of lower degree of support from his team-mates, as reflected in Everton's total points, 1771, in contrast to the 2194 scored by all Tottenham players, making them the winning team of the last season.

Of course, these are just a few examples of head-to-head analysis, intended to supplement your selection-making strategy. As mentioned above, the plots themselves speak much more than a thousand words, by themselves only.

# Summary and Further Directions
Hopefully, this post has managed to deepen your insights into last season's top player performance, in terms of total number of points scored. For this purpose, I presented a multi-dimensional view, providing information as to how a given player ranked, on the overall, relative to teammates with the most similar tasks and responsibilities[^football_strategy], as well as competing players.

In further posts from the same [series][fepl_selection_series], we'll look into various other statistics and metrics, accompanied by descriptive visualizations, for the very same
purpose stated above - assisting you, the reader, in making the best possible selection for the next game-week!

[^fepl_points]: For detailed [reference][fepl_help] on point scoring, navigate to the _Rules_ tab, and then the _Scoring_ section.

[^football_strategy]: Of course, whilst providing statistically-backed informational value, this statement is a wild over-generalization, when we consider the
elaborate nature of modern football strategies and formations, where individual instructions and tasks vary both along temporal, intra- as well as inter-match, scales.


[fantasy_football_wiki]: https://en.wikipedia.org/wiki/Fantasy_football_(Association)
[fepl_selection_series]: /tagged/fpl-selection
[fepl_section]: /tagged/fantasy-football
[fepl_site]: https://fantasy.premierleague.com/
[fepl_help]: https://fantasy.premierleague.com/help/
[fepl_register]: https://users.premierleague.com/a/profile/register
[fepl_player_list]: https://fantasy.premierleague.com/player-list/
[epl_fixtures]: https://www.premierleague.com/fixtures
[lukaku_transfer]: https://www.bbc.co.uk/sport/football/40550934
