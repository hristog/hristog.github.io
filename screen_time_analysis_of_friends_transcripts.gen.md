
Inspired by a recent characters-across-seasons-based Game Of Thrones [visualization][got_vis_reddit], I decided to perform a similar
study on a dataset which I'd recently collected. It consists, namely, of
transcripts of all episodes from all seasons of one of my favorite TV series,
[Friends][friends_wiki].

# Dataset
The aforementioned dataset, consists of transcripts, spread across
a nested structure of seasons[^s2_formatting], episodes, and scenes. Each scene, naturally,
contains a sequence of lines, by characters predominantly addressing each
other. For examples, here's a simplified example of a scene:
```text
[Scene: A Park, Alice and Bob are having a picnic.]
Alice: We're quite lucky with the weather today, aren't we?
Bob: Indeed, we are.
```

[^s2_formatting]: Due to poorly-formatted raw data for the second season, for the
purposes of this study the corresponding episodes were excluded from the analysis.
Nevertheless, I plan to customize my script further, in order to be able to subsequently include the missing data.

# Methodology
The focus of this study is to investigate two proxies of character importances,
namely, total number of lines alloted, and sum of the lengths[^line_length] of
all lines alloted, for each individual season.

[^line_length]: While, line length can be viewed as a form of a proxy for total
amount of screen time alloted to a given character, please, note that in this
study the actual temporal dimension was not considered in any way whatsoever.
For completeness, line length is defined as the total number of characters -
including punctuation (which is assumed to account for additional screen time) -
comprising a given character line. And line, itself, is defined as a contiguous
array of sentences, alloted to a a set of characters (usually, a single
character).

Of course, given the raw nature of the unprocessed data, the aforementioned metrics
are only approximations. Nevertheless their degree of significance is strong enough
for the purposes and scope of this study.

# Visualizations
<div class="img-box">
<a href="https://hristog.github.io/uploads/Friends_num_lines_all.png" target="_blank"><img src="https://hristog.github.io/uploads/Friends_num_lines_all_150x256.png" alt="Number of lines for all characters"></a>
<a href="https://hristog.github.io/uploads/Friends_num_lines_all_s5on.png" target="_blank"><img src="https://hristog.github.io/uploads/Friends_num_lines_all_s5on_144x256.png" alt="Number of lines for all characters"></a>
<a href="https://hristog.github.io/uploads/Friends_num_lines_supp.png" target="_blank"><img src="https://hristog.github.io/uploads/Friends_num_lines_supp_148x256.png" alt="Number of lines with focus on supporting characters"></a>
<a href="https://hristog.github.io/uploads/Friends_line_length_all.png" target="_blank"><img src="https://hristog.github.io/uploads/Friends_line_length_all_150x256.png" alt="Total line length for all characters"></a>
<a href="https://hristog.github.io/uploads/Friends_line_length_supp.png" target="_blank"><img src="https://hristog.github.io/uploads/Friends_line_length_supp_148x256.png" alt="Total line length with focus on supporting characters"></a>
</div>

We can clearly observe well formed[^pair_formation] pairs of characters[^char_pairs], by as early as the end of the fourth season: [Ross and Rachel][ross_rachel], [Monica and Chandler][monica_chandler], and Joey and Phoebe; the total line length graphs reveal a further pair, formed by [Joey and Chandler][joey_chandler][^jman_channie], which is not clear enough given only the context of the screen-time
analysis, though.

Since the [beginning of the fifth season][s05_start], however, when a significant
event takes place in the personal life of one of the leading cast members, we see a
dramatic reshuffling of the "leaderboard". In particular, the beginning of the
season in question, approximately overlaps with the beginning of Jennifer Aniston's [relationship][ja_relationships] with Brad Pitt[^will_colbert], eventually leading to their marriage, immediately after the [end of season six][s06_end] (around halfway through 2000).

To put it mildly, as a result[^ja_correlation], the total amount of screen time[^screen_time_proxies]
alloted to Aniston's character, Rachel, skyrockets for seasons 7 and 8.

Another dramatic anomaly observed in the graphs is the significantly reduced
season eight screen time, alloted to Chandler (portrayed by the wonderful Matthew Perry). A quick reference check on [what was going on][matthew_perry] in the actor's life around that time, reveals that he had been battling with opioid
addiction (and, reportedly, entered rehab near the end of the
[seventh season][s07_end]).

[^pair_formation]: The notion of a pair here, however, is relatively vague, given
the quintessentially fluent nature of interactions taking place within the context
of a sitcom environment.
[^char_pairs]: Of course, this is by no means an estimate of amount of intra-pair interaction between said characters. It should be thought of more as a sort of
ranking, based on character importance, corresponding the particular period of
the timeline of the TV series.
[^jman_channie]: At this point, the average die-hard fan of the show is probably reminded of quintessential moments like Joey's _"No more J-man and Channie's"_
[line][jman_channie], after Chandler informed Joey he'd been moving out to live together with Monica.
[^will_colbert]: Traditionally, just as the other various celebrities who were
[partners of cast members][friends_relationships] at one point or another, Brad Pitt eventually [made an appearance][bradpitt_cast] on the show,
portraying Will Colbert, who was presented as a former high school mate of Ross, Monica and Rachel.
[^ja_correlation]: Naturally, this is only a correlation outlined by the data.
This study does not mean or intend, in any way whatsoever, to underestimate
Jennifer Aniston's acting skills or visual characteristics (or any other factor
that might have contributed to her amazing success, for that matter).
[^screen_time_proxies]: As estimated via the total number of lines, as well as
the cousin statistic, total line length.

# Source code
The plan is to eventually release my Jupyter Notebook and source code (once I bring them to a neat enough implementation state), used for performing the
analysis, on [GitHub][github_account], write an accompanying blog post here to
support the various implementation-design decisions, and provide minimally sufficient background for the employed technologies.

[friends_wiki]: https://en.wikipedia.org/wiki/Friends
[got_vis_reddit]: https://www.reddit.com/r/dataisbeautiful/comments/6n150e/oc_screen_time_of_got_characters_fixed/
[ja_relationships]: https://en.wikipedia.org/wiki/Jennifer_Aniston#Relationships
[matthew_perry]: https://en.wikipedia.org/wiki/Matthew_Perry#Personal_life
[joey_chandler]: http://friends.wikia.com/wiki/Chandler_and_Joey%27s_apartment
[monica_chandler]: http://friends.wikia.com/wiki/Monica_and_Chandler
[ross_rachel]: http://friends.wikia.com/wiki/Ross_and_Rachel
[friends_relationships]: http://friends.wikia.com/wiki/Relationships
[jman_channie]: http://friends.wikia.com/wiki/The_One_Where_Ross_Hugs_Rachel
[s05_start]: https://en.wikipedia.org/wiki/List_of_Friends_episodes#Season_5_.281999.E2.80.9300.29
[s06_end]: https://en.wikipedia.org/wiki/List_of_Friends_episodes#Season_6_.281999.E2.80.9300.29
[s07_end]: https://en.wikipedia.org/wiki/List_of_Friends_episodes#Season_7_.282000.E2.80.9301.29
[bradpitt_cast]: http://friends.wikia.com/wiki/The_One_With_The_Rumor
[github_account]: https://github.com/hristog


---

