
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

## Visualizations
<div class="img-box">
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_overall.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_overall_170x256.png" alt="Total Points (FEPL 2016/2017, whole season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_1h.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_1h_170x256.png" alt="Total Points (FEPL 2016/2017, first half of season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_2h.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_2016_2h_170x256.png" alt="Total Points (FEPL 2016/2017, second half of season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_overall.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_overall_172x256.png" alt="Contribution to Team Total Points (FEPL 2016/2017, whole season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_1h.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_1h_172x256.png" alt="Contribution to Team Total Points (FEPL 2016/2017, first half of season)"></a>
<a href="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_2h.png" target="_blank"><img src="/uploads/fepl_tp_contributions/fepl_tp_contribution_pct_2016_2h_172x256.png" alt="Contribution to Team Total Points (FEPL 2016/2017, second half of season)"></a>
</div>

<!--
- Explanation of position abbrevs
- Explanation that int he 2nd set of plots, the percentages are relative to the total squad points.

- Lukaku vs H. Kane, Costa, Aguero
- Sanchez vs Hazard, Alli, Eriksen, De Bruyne
-->


# Summary and Further Directions
Hopefully, this post has managed to deepen your insights into last seasons's top player performance, in terms of total number of points scored. For this purpose, I presented a
multi-dimensional view, providing information as to how a given player ranked, on the overall, relative to teammates with the most similar tasks and responsibilities[^football_strategy],
as well as competing players.

In further posts from the same [series][fepl_selection_series], we'll look into various other statistics and metrics, accompanied by descriptive visualizations, for the very same
purpose stated above - assisting you, the reader, in making the best possible selection for the next game-week!

[^football_strategy]: Of course, whilst providing statistically-backed informational value, this statement is a wild over-generalization, when we consider the
elaborate nature of modern football strategies and formations, where individual instructions and tasks vary both along temporal, intra- as well as inter-match, scales.


[fantasy_football_wiki]: https://en.wikipedia.org/wiki/Fantasy_football_(Association)
[fepl_selection_series]: /tagged/fepl-selection
[fepl_section]: /tagged/fantasy-football
[fepl_site]: https://fantasy.premierleague.com/
[fepl_register]: https://users.premierleague.com/a/profile/register
[fepl_player_list]: https://fantasy.premierleague.com/player-list/
[epl_fixtures]: https://www.premierleague.com/fixtures


---

