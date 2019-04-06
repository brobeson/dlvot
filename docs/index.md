# dlvot

## Installation

1. Download [dlvot](https://github.com/brobeson/dlvot/blob/master/dlvot).
1. Install the *requests* and *wget* packages for Python:
   ```
   $ pip install requests wget
   ```

## Usage

At its most basic, just tell dlvot which data sets to download. This example
will download the 2017 and 2018 VOT data sets:

```
$ dlvot 2017 2018
```

On Windows:

```
C:\Users\you> py dlvot 2017 2018
```

Run `dlvot --help` for complete information.

### Note for Windows Users

On Windows, you must run dlvot with elevated privileges. Otherwise, you will get
an `OSError` exception when the application tries to create a symlink.

## How dlvot Works

VOT reuses sequences, just updating the tags and ground truth data. dlvot takes
advantage of this to save space on your system. Only one copy of the frame data
is kept. Symlinks mimic the directory structure typically expected by the VOT
toolkit.

The root download directory is *~/Videos/vot/*. Within this directory is a
*sequences/color/* subdirectory. At this time, color is the only supported
channel. Also in the root directory is a subdirectory for each data set year.
So, the directory structure looks like this:

```
~/Videos/vot/
  sequences/color
    bicycle/
      00000001.jpg
      00000002.jpg
      <rest of the images>
  2013/
    bicycle/
      color -> ~/Videos/vot/sequences/color/bicycle
      groundtruth.txt
      <tag files>
  2014
    bicycle/
      color -> ~/Videos/vot/sequences/color/bicycle
      groundtruth.txt
      <tag files>
```

dlvot creates any necessary directories, downloads the archives from VOT,
unpacks the archives, creates the symlinks, and deletes the archives.
