# General

Oh hai!

[![CI](https://github.com/Binaergewitter/serious-bg/workflows/CI/badge.svg?branch=master)](https://github.com/Binaergewitter/serious-bg/actions/)
[![Support us on Patreon](http://ionicabizau.github.io/badges/patreon.svg)](https://www.patreon.com/Binaergewitter) 
[![Donate](https://img.shields.io/liberapay/patrons/Binaergewitter.svg?logo=liberapay)](https://liberapay.com/Binaergewitter)


# Markdown syntax
You can add a "release: 2" line to the article markdown in case you 
fudged up a release and would like to increment the GUID in the feed after a fix

You can add a "published: false" line to the article markdown to NOT have it
show up anywhere.

# Feeds
Feed with all items:

    /podcast_feed/all/m4a/rss.xml

Examples for the category feed generation:

    /podcast_feed/spezial/mp3/rss.xml
    /podcast_feed/talk/opus/rss.xml

iTunes feed that uses m4a with a fallback to mp3 if there is no m4a for that episode

    /podcast_feed/talk/itunes/rss.xml

Note: You can also add a feed_size parameter and a page parameter to the URL ("?feed_size=4&page=3")


# Stork search
Prerequisits: [install stork](https://stork-search.net/docs/install)

For every release the stork index has to be built like this:

```
python gen-stork.py > stork.toml
stork --build stork.toml
```

then a github action builds and publishes `bgt.st` to https://search.binaergewitter.de/bgt.st.
