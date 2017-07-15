
Inspired by a recent characters-across-seasons-based
[Game Of Thrones visualization][got_vis_reddit], I decided to perform a similar
study on a dataset which I'd recently collected. It consists, namely, of
transcripts of all episodes from all seasons of one of my favorite TV series,
[Friends][friends_wiki].

[TOC]

# Dataset
The aforementioned dataset I collected, consists of transcripts, spread across
a nested structure of seasons, episodes, and scenes. Each scene, naturally,
contains a sequence of lines, by characters predominantly addressing each
other. For examples, here's a simplified example of a scene:
```
[Scene: A Park, Alice and Bob are having a picnic.]
Alice: We're quite lucky with the weather today, aren't we?
Bob: Indeed, we are.
```

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
## Number of lines
### All characters
![number of lines for all characters][num_lines_all_chars]

### Focus on supporting characters
![number of lines with focus on supporting characters][num_lines_supp_chars]

## Total line length
### All characters
![total line length for all characters][line_length_all_chars]

### Focus on supporting characters
![total line length with focus on supporting characters][line_length_supp_chars]

[num_lines_all_chars]: https://hristog.github.io/uploads/Friends_num_lines_all.png "Number of lines for all characters"
[num_lines_supp_chars]: https://hristog.github.io/uploads/Friends_num_lines_supp.png "Number of lines with focus on supporting characters"
[line_length_all_chars]: https://hristog.github.io/uploads/Friends_line_length_all.png "Total line length for all characters"
[line_length_supp_chars]: https://hristog.github.io/uploads/Friends_line_length_supp.png "Total line length with focus on supporting characters"

# Discussion
TODO

[friends_wiki]: https://en.wikipedia.org/wiki/Friends
[got_vis_reddit]: https://www.reddit.com/r/dataisbeautiful/comments/6n150e/oc_screen_time_of_got_characters_fixed/
[ja_bp_marriage]: https://en.wikipedia.org/wiki/Jennifer_Aniston#Relationships
[matthew_perry]: https://en.wikipedia.org/wiki/Matthew_Perry#Personal_life

---

