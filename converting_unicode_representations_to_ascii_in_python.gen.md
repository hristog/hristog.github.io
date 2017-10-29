
# Python and Unicode

Oh, my - If I had a nickel/five-pence every time I had to deal with various kinds
of Unicode-related processing in Python ...

Anyway, this brief note is for those of you who've ever run into a not-so-helpful error message, along the lines of the following:
```ipython
UnicodeEncodeError: 'ascii' codec can't encode character u'\xef' in position 2: ordinal not in range(128)
```

I'd bet those of you who have used Python for a bit larger than trivial project have invariably encountered
some variety of it.

Let's see how we could approach this issue in different ways. For this purse, I'll first go
ahead and  define a
simple use-case: we're experimenting with a given dataset and we want to run a number of
Machine Learning methods against the dataset and output a nice log file with performance
summary and results for each method.

As it turns out, not all ML method names were created equal, and for some of them
we need more characters than those defined in the basic ASCII table:

```ipython
In [1]: method = u'Naïve Bayes'

In [2]: method
Out[2]: u'Na\xefve Bayes'

```

So far so good - Python has successfully been able to encode our special character
`ï` as `\xef`. However, once we attempt to put that into a non-unicode string, all hell
breaks loose:
```ipython
In [3]: method_filename = '{}_method.log'.format(method.replace(' ', '_'))
---------------------------------------------------------------------------
UnicodeEncodeError                        Traceback (most recent call last)
<ipython-input-31-c5a4e402b551> in <module>()
----> 1 method_filename = '{}_method.log'.format(method.replace(' ', '_'))

UnicodeEncodeError: 'ascii' codec can't encode character u'\xef' in position 2: ordinal not in range(128)
```

At this point, we have a couple of options: ignore-and-remove the problematic character or
try to somehow convert it to an approximate representation that is part of the
ASCII character set. Let's explore the former option first:
```ipython
In [4]: '{}_method.log'.format(method.replace(' ', '_').encode('ascii', 'ignore'))
Out[4]: 'Nave_Bayes_method.log'

```
Fair enough, it works and we get what we pay for it, but surely we could do better,
right?

Alternatively, if we're happy with non-ASCII file names occupying our file system, we
could just do:
```ipython
In [5]: method_filename = u'{}_method.log'.format(method.replace(' ', '_'))

In [6]: method_filename
Out[6]: u'Na\xc3\xafve_Bayes_method.log'

In [7]: print(method_filename)
Naïve_Bayes_method.log

```

However, that's not really the point of this exercise. Let's see if we could do even better.
```ipython
In [8]: import unicodedata

In [9]: method_filename = '{}_method.log'.format(
            unicodedata.normalize(
                'NFKD', method.replace(' ', '_')).encode(
                     'ascii', 'ignore'))

In [10]: method_filename
Out[10]: 'Naive_Bayes_method.log'
```

This is where the [`unicodedata`][unicodedata_module] module from the Python Standard
Library comes to the rescue. In this case, either of the `NFD` or `NFKD` normalizations would work, as
described in the documentation:
> [Canonical decomposition] translates each character into its decomposed form.

This is exactly what we needed, wasn't it? An equivalent ASCII representation of our fancy
ML method names.

Finally, I would like to give credit to a StackOverflow [answer][stackoverflow_unicodedata], from which I
learned about the `unicodedata.normalize` functionality that gave rise to the current post.

Happy debugging of `UnicodeError`s, everybody :)

[unicodedata_module]: https://docs.python.org/2/library/unicodedata.html
[stackoverflow_unicodedata]: https://stackoverflow.com/a/7782177


---

