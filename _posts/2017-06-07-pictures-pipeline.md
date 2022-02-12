---
title: Pipeline to Organize Pictures
excerpt: "Example setup how to organize an endless stream of pictures (and videos)."
description: "Example setup how to organize an endless stream of pictures (and videos)."
categories: [Media]
tags: [files and folders, pictures]
---

### Collect
Move pictures from all over the place into one working directory. Be careful not to override pictures with the same name!
E.g., use
`mv --backup=numbered some_dir/* working_directory`
and
`mv --backup=numbered` creates hidden backup files that might be ignored by follow-up programs. 'unhide' those files, e.g. using [Dr.Rename's](https://github.com/kerner1000/drrename) build-in 'unhide-rename-strategy'.
	
###	(Fix Permisssions)
`sudo chown alex:users -R .`

### (Delete Metadata)
`find . -type d -name '.@__thumb' -exec rm -r "{}" \;`

`find . -name DS_Store -exec rm -r "{}" \;`

### [Convert *.heic* files]({{ site.url }}/2019/01/11/heic-pictures)

### [Check files for duplicates]({{ site.url }}/2017/06/07/duplicate-files)

### [Rename pictures by meta date]({{ site.url }}/2017/06/07/rename-pictures-by-date)

### Sort By Date
Start to sort by date. Move to folders named by date, e.g. 2015-05. Again be careful to not override when moving.

Also note, that too many files in one folder will kill performance of your graphical file manager such as Nautilus of Finder. I recommend to keep number of files per folder below 2k.

You can check the number of files inside a folder with

`ls 2016 | wc -l`

(assuming your file names do not have white spaces)

#### Example Linux
```
mv --backup=numbered 201505*jpg ../2015-05/
```
#### Example Mac
```
rsync -a --backup --remove-source-files --progress 2012-*/*.jpg 2012
```

#### Example
```
mv 2021-0?/* 2021
```



### More Helpful sniplets

Unzip all `zip`s into current directory:
```
unzip -B \*.zip
```
Delete empty folders:
```
find . -empty -type d -delete
```


*..work in progress..*
