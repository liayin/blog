---
layout: post
title: AWS Basic Commands
date: 2023-5-23 10:22:01 --0000
permalink: /posts/aws-basics/
---

This post includes basic AWS commands that are commonly used.

Using AWS CLI to download files from S3 ([Reference](https://www.edureka.co/community/9828/how-to-download-folder-from-aws-s3)):
```shell
aws s3 cp s3://bucketname/dir localdirectory --recursive
```
Use --recursive in case of any error. 