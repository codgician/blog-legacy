---
title: Codeforces 913C - Party Lemonade
date: 2018-01-09 11:58:00
tags: 
- ACM-ICPC
- Greedy
- Bitmasks
- Codeforces
category: Solutions
mathjax: true
---

# 题面

因为手残和脑残 ranking 暴降 75，呜呜呜呜呜呜呜~

[题目链接](http://codeforces.com/contest/913/problem/C)

大致题意：

现有 $n \ (1 \le n \le 30)$ 种瓶装柠檬汽水，每种汽水都有无限瓶。第 $i$ 种瓶装柠檬汽水有 $2^{i - 1}$ 升并且售价 $c_i \ (1 \le c_i \le 10^9)$。现在你需要至少 $L \ (1 \le L \le 10^9)$ 升汽水，请问你至少要花多少钱？

# 贪心！

## 大致思路

注意到第 $i$ 种瓶装柠檬汽水有 $2^{i - 1}$ 升这一特殊的条件。这意味着，第 $i$ 种柠檬汽水事实上可以由 $2$ 瓶第 $i - 1$ 种柠檬汽水替换，或者由 $2^2$ 瓶 第 $i - 2$ 种柠檬汽水替换，…… 也就是说，我们可以通过贪心来更新第每种汽水的最优单价——将第 $i$ 种柠檬汽水的单价更新为第 $1 \sim i$ 种柠檬汽水中最省钱的购买方案（对于第 $k \ (1 \le k \le i)$ 种购买 $2^{i - k}$ 瓶）。

但是光这样还是不够的，因为可能出现购买多于 $L$ 升反而比购买 $L$ 升便宜的情况。

我们不妨把 $L$ 先转换成一个二进制数。如果要购买严格等于 $L$ 升柠檬汽水的话，只需要将二进制 $L$ 为 $1$ 的位数对应的柠檬汽水都买一瓶就好了（即二进制 $L$ 的从右往左第 $i$ 位为 $1$，那么就购买 $1$ 瓶第 $i + 1$ 种汽水）。 这样我们得到的严格等于 $L$ 升柠檬汽水的购买方案一定是最优的，因为经过之前的贪心购买与每一种柠檬汽水等量的柠檬汽水所需花费的金额是最优的。

而购买大于 $L$ 升汽水更优的情况，也就是在上述过程中，购买第 $1 \sim k$ 位对应柠檬汽水所花的钱（$1$ 则买，$0$ 则不买）比只购买一瓶第 $k + 1$ 位对应的柠檬汽水所花的钱还要多。在这种情况下我们只需要买一瓶第 $k + 1$ 位对应的柠檬汽水就行了（并且得到了更多的柠檬汽水），而之前位对应的柠檬汽水都无需购买。

## 具体实现

[Submission #34039523](http://codeforces.com/contest/913/submission/34039523)

[GitHub - Backup Link](https://github.com/codgician/ACM-ICPC/blob/master/Codeforces/913C/greedy.cpp)
