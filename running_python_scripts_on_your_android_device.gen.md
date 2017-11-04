
# Termux: a terminal emulator for Android OS

![Termux: a terminal emulator for Android OS](/uploads/linux/termux.png "Termux: a terminal emulator for Android OS")

I came across [Termux][termux] via a relatively recent mention on HackerNews. Can't remember which one it was exactly, but if you'd like to familiarize yourself with its particular design decisions,
advantages, disadvantages, features, etc., you might want to head over to HackerNews and give a quick skim over the following comment threads: [1][termux_hn_1], [2][termux_hn_2], [3][termux_hn_3], [4][termux_hn_4], [5][termux_hn_5].

If you opted to do a Depth-First-Search of the above articles, then I may have already lost you as a reader already. If, however, you didn't get put off by my desperate attempts at humor, and somehow found your way back to this post, then welcome back. `else # i.e., you prefer synthesized content`, keep reading :).

# Python[^google_play_screenshot] on Termux
Once you've got Termux [installed][termux_google_play] in your Android environment, you simply need a
couple of straightforward steps to update your packages and install Python. Fortunately, Termux provides support for both versions of Python - v2 (intensely branded as "Legacy Python" in the recent history of the language) and v3.

[^google_play_screenshot]: Never mind that the bottom tab, in the Google Play screenshot displayed above, is occupied by source code in another programming language (which we'll pretend we're unfamiliar with, and looks like a variety of Assembly langauge to us), which for all intents and purposes of this post can be thought of as Python :)

```bash
$ apt update && apt upgrade
$ termux-setup-storage
$ pkg install python
$ pkg install python2
```

Upon successful completion of the above steps, you should be able to access your Python scripts and
other files from `$HOME/storage`.

# `pip` gotcha's

As you probably have guessed already, each Python package comes hand in hand with its accompanying `pip` utility: `pip` for Python v3 and `pip2` for "Legacy Python".

However, observe the following check-with-a-pawn kind of situation:
```shell
$ pip --version
pip 9.0.1 from /data/data/com.termux/files/usr/lib/python2.7/site-packages (python 2.7)
$ pip2 --version
pip 9.0.1 from /data/data/com.termux/files/usr/lib/python2.7/site-packages (python 2.7)
```

[Cowabunga][cowabunga]! Both `pip` package managers are associated with Python 2.7 and none with
non-"Legacy Python". This may arise if you updated `pip2` which then overwrites the `pip` reference itself.

Fear not, young Houdini's, tomorrow never dies! There's an escape from this one, too. Simply use:
```bash
$ python -m pip install <package>
$ python2 -m pip install <package>
```

You can subsequently turn these into aliases, and add to your `$HOME/.bashrc` via:
```bash
alias pip_install=python -m pip install
alias pip_install2=python2 -m pip install
```

# Editing your scripts

Being a multi-functional terminal emulator, Termux does provide support for
traditional editors such as `vi` and `vim`. However, despite the aforementioned
equivalents to full-fledged keyboards (physical or otherwise), I've found the use
of CLI-based text editors[^vim_vs_emacs] to be a bit awkward without an external keyboard.

[^vim_vs_emacs]: No, I do not intend to dive into a detailed dispute of the eternal
Vim-vs-Emacs question. But Vim is the better one ... :)

For the purpose of editing my Python scripts, I've found [DroidEdit][droid_edit_google_play]
to do the job just well enough. Of course, Google will probably be able to provide you
detailed comparisons, reviews, trade-offs and alternatives. But you wouldn't go wrong if you give DroidEdit a go, as a first attempt.

[termux]: https://termux.com/
[termux_keyboard]: https://termux.com/touch-keyboard.html
[termux_storage]: https://termux.com/storage.html
[termux_google_play]: https://play.google.com/store/apps/details?id=com.termux
[termux_python]: https://wiki.termux.com/wiki/Python
[droid_edit_google_play]: https://play.google.com/store/apps/details?id=com.aor.droidedit
[termux_hn_1]: https://news.ycombinator.com/item?id=9905391
[termux_hn_2]: https://news.ycombinator.com/item?id=11572939
[termux_hn_3]: https://news.ycombinator.com/item?id=15529426
[termux_hn_4]: https://news.ycombinator.com/item?id=11570596
[termux_hn_5]: https://news.ycombinator.com/item?id=11459355
[cowabunga]: http://turtlepedia.wikia.com/wiki/Cowabunga_(catchphrase)

---

