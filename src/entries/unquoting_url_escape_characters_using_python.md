---
title: Unquoting URL escape characters using Python
publish_date: Nov 5th, 2017
tags:
  - python
  - python-v2
  - unicode
  - text-processing
---

# `%xx`-escapes

Have you ever come across those strange looking `%xx`-escapes, that are used
in URLs. Yes, I don't like them either ...

I can imagine a class of use cases where such kind of escape characters may
need to be handled: say, you'd like to annotate - in a local or remote document - a number of URLs, with a given substring (of the URL itself).

Let's look at the case where the cardinality of our URLs set is unity:
```ipython
# Python 2.7.12
In [1]: url
Out[1]: 'https://www.a-random-ml-website.com/na%C3%AFve-bayes'
```

Since I don't suppose any of you would be particularly keen on annotating this URL with
`na\xc3\xafve-bayes`, we'll have to resort to utility functions provided by [`urllib2`][urllib2_module][^python_version]:

[^python_version]: The Python version associated with the code examples from this post is `Python 2.7.12`.

```ipython
In [2]: import urllib2

In [3]: urllib2.unquote(url)
Out[3]: 'https://www.a-random-ml-website.com/na\xc3\xafve-bayes'
```

Ugh. We've suddenly time-travelled back to [a few days ago][unicode_representations]!
Luckily enough, our memories of the previous timeline branch have been preserved intact -
we are empowered with the knowledge of the `unicodedata` module:

```ipython
In [4]: url = urllib2.unquote(url).decode('utf8')

In [5]: url
Out[5]: u'https://www.a-random-ml-website.com/na\xefve-bayes'

In [6]: import unicodedata

In [7]: better_looking_url = unicodedata.normalize('NFKD', url).encode('ascii', 'ignore')

In [8]: better_looking_url
Out[8]: 'https://www.a-random-ml-website.com/naive-bayes'

```

Now, you can slice and dice `better_looking_url` as you please, for your annotation purposes.

[unicode_representations]: /converting_unicode_representations_to_ascii_in_python.html
[urllib2_module]: https://docs.python.org/2/library/urllib2.html
