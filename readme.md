# dl-vot

[![Build
Status](https://travis-ci.com/brobeson/dlvot.svg?branch=master)](https://travis-ci.com/brobeson/dlvot)

This script allows you to download [VOT Challenge](http://votchallenge.net/)
sequences, without requiring the VOT toolkit.

### :exclamation: Note

The software doesn't do anything, yet. It's not even to alpha stage. The
documentation below is what you can expect as I make progress.

## Requirements

Python 3 is required. The software is automatically tested on Python 3.6 and
3.7. Older versions of Python 3 _should_ work, but aren't guaranteed.

Some 3rd party Python libraries are also needed. You can install these just by
running
```
$ pip install --requirement requirements.txt
```

## Installation

Right now, this software must be manually downloaded from this repository. The
necessary file is [dlvot](dlvot).

## Running

### Available Datasets

This tool can download and unpack data for the 2013 - 2018 VOT Challenges.

The most basic way to run the program is to just give it a challenge year to
download:

```
$ dlvot 2013
```

Multiple years can be specified, too:

```
$ dlvot 2013 2014
```

There is also an `all` option, which will download all the known datasets:

```
$ dlvot all
```

Full help is available with the `--help` option:

```
$ dlvot --help
```

