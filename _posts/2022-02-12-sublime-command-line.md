---
title: 'Call <i>Sublime Text</i> and <i>Sublime Merge</i> from Terminal'
description: 'Opening a file with <i>Sublime Text</i> and <i>Sublime Merge</i> from the Terminal on macOS.'
excerpt: 'Opening a file with <i>Sublime Text</i> and <i>Sublime Merge</i> from the Terminal on macOS.'
categories: [Development]
tags: [terminal]
lang: en
---

<i>Sublime Text</i> and <i>Sublime Merge</i> both can be called on a Command Line/ Terminal to open files.
This does not work out of the box, however, since an appropriate symlink is missing.
Fortunately, this can be done easily via the following commands:

### <i>Sublime Text</i>
```
 ln -sv /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl
```

### <i>Sublime Merge</i>
```
ln -sv /Applications/Sublime Merge.app/Contents/SharedSupport/bin/smerge /usr/local/bin/smerge
```

You might get an `no such file or directory` error. In this case, just create the directory. The Shell is configured to pick up this directory when collecting binaries for the `PATH` variable.
```
sudo mkdir -p /usr/local/bin
```

After this, you might need to restart your terminal session. Then, you should have the two commands `subl` and `smerge` available.

## Launching a Sublime Merge diff of two non-repository, arbitrary files

You can open a Sublime Merge diff window of any two files, even without having them in a git repository.
For this, start Sublime Merge from command line like this:
```
smerge mergetool file1 file2
```