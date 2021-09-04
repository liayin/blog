---
layout: post
title: Linux Basics
date: 2021-08-13 9:40:00 --0000
permalink: /posts/linux-basics/
---

Show all the files and creation time:
```
dir -l
```

Make a file
```
touch job.pbs
```

View the contents of the file
```
cat job.pbs
```

Edit the file with vim
```
module load vim
vim
```

Delete files
```
unlink filename
rm filename
```

#### Vim:
To start editing:
```
:i
```

To save the file and exit the editor:
```
:x
```

To quit without saving:
```
:q!
```

[Tutorial](https://www.linux.com/training-tutorials/vim-101-beginners-guide-vim/)

#### PBS
Retain errors:
```
#PBS -k eo
```