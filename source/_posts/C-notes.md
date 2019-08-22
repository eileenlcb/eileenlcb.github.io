---
title: C++ notes
date: 2019-07-13 17:09:56
tags: 学习
---
1.char *test中，printf("%p",test),输出的是test的地址；printf("%s",test),输出test的值。实质上，test为该字符串的首地址，printf("%s",test)中，获得test地址后，输出test为首地址的字符串。