---
layout: post
author: rgalindor
title: Use gdrive from command line
subtitle: There is no need for a web browser
excerpt: Use gdrive in linux without graphical interface
background: '/img/posts/crop-faceless-dev-on-software.jpg'
comments: true
usemathjax: true
---

So, do you think that [Google Drive](https://www.google.com/intl/en/drive/) is a tool to share only `.docx`, `.xlsx`, and `.pptx` files? Well, yes, but it allows you to share even files with a big volume across different devices. I used to believe that one limitation for it is the need for a web browser in any device, but I was so wrong.

You need only two things to share _big files_:

1. A [google account](https://accounts.google.com/).
2. An internet conection.

Maybe you are aware that on mobile devices you can access files through **mobile apps**. So it is too in a **Linux** server without a graphical interface at all. There is a [`gdrive`](https://github.com/prasmussen/gdrive) command-line utility that allows you to interact with Google Drive. This is especially useful when you connect to remote servers through `ssh` and you have no _graphical interface_ but your _command line_.

| Device | Best utility |
|--|--|
| Mobile device | App |
| Personal computer | Web app |
| Linux server | Command-line utility |

## Install `gdrive`

This utility can be installed by cloning the [GitHub](https://github.com) repo, then compiling it, and so on. However, the simplest way to install it is through a `conda` installation:

```bash
conda create --name gdrive
conda activate gdrive
conda install -c conda-forge gdrive
conda deactivate
```

And that's it, you just installed `gdrive`.

## Connect to your account

The first thing you need to do is get inside your custom environment and starting to enjoy:

```bash
conda activate gdrive
gdrive list
```

Then you need to authenticate, to do this you need to copy the **url** and paste it in the _url box_ within your preferred (and local) web browser. Such _link_ gives you to an authenticate landing page, if you successfully authenticate to your account you will receive a passphrase that you need to _ copy/paste_ into the prompt from your command line. Finally, the utility provides you with a list of files in your _"root"_ path in Google Drive. 

When you do this, `gdrive` utility creates _auth tokens_ within your `~/.gdrive/` folder, such files allow the utility to keep logged in and sync your account. So, if you want to perform any other operation you do not need to authenticate again. That is why whether you use a shared server you must clean your _auth tokens_ to avoid security issues:

```bash
rm ~/.gdrive/*
```

Otherwise, you have the access open to `list`, `delete`, `download`, `upload`, files within your Google Drive Account.

A very cool thing you can perform is share files with people. So maybe you have a `Shared with me` folder that is not visible with a simple `gdrive list`. To have access to such folder, you can do the following:

```bash
gdrive list --query "sharedWithMe"
```

```
Id                             Name                    Type   Size     Created
0B3X9GlR6EmbnZ3gyeGw4d3ozbUk   drive-windows-x64.exe   bin    6.6 MB   2015-07-18 16:43:58
0B3X9GlR6EmbnTXlSc1FqV1dvSTQ   drive-windows-386.exe   bin    5.2 MB   2015-10-19 16:43:53
0B3X9GlR6EmbnVjIzMDRqck1aekE   drive-osx-x64           bin    6.5 MB   2018-03-11 16:43:50
0B3X9GlR6EmbnbEpXdlhza25zT1U   drive-osx-386           bin    5.2 MB   2019-07-28 16:43:41
0B3X9GlR6Embnb095MGxEYmJhY2c   drive-linux-x64         bin    6.5 MB   2020-11-17 16:43:38
0B3X9GlR6EmbnMldxMFV1UGVMTlE   linux                   dir             2016-02-21 22:54:00
```

This operation allows you to display key information about the files within **Shared folder**, notably, you can view the `Id` of every item (file), and as you can guess, this is the most important field to perform operations.

Maybe you could inspect the contents of an entire folder, (the `linux` directory in this example) this is easy:

```bash
gdrive list --query "'0B3X9GlR6EmbnMldxMFV1UGVMTlE' in parents"
```

Perhaps then you could download a file to your remote server (I don't know, maybe to perform a bioinformatic pipeline). You get it, you need the `Id`:

```bash
gdrive download 0B3X9GlR6EmbnbEpXdlhza25zT1U
```

And this is how you can transfer somehow big files to your production server!

> Photo by Sora Shimazaki from Pexels