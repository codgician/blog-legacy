---
title: 碎思杂念
date: 2018-04-01 10:15:10
tags: 
- ACM-ICPC
category: Life
thumbnail: /2018/04/01/few-thoughts-april-2018/cover.jpg
#mathjax: false
---

# 0x00

**ACM-ICPC 是一场思维竞赛**。

起初得知 ACM-ICPC 赛中允许携带模板的时候，我是非常吃惊的。但是当时的我比较 naive，并没有深究这背后的原因是什么，平时训练的时候依然是以学习算法为主。

然而当本辣鸡前几周接触到网络流中的最大流部分后，我的三观被颠覆了。

最大流的算法本身不算特别难（本辣鸡只会源自 Ford Fulkerson 方法的 Edmonds Karp 算法以及 Dinic 算法 QAQ），其思想也不过是不停地寻找增广路径（增广路径不妨理解为可以被进一步优化的路径）以此不断地优化方案，最终求出最大流。

但是当我兴致勃勃地冲向题库时…… 发现我基本一道题都做不来。

最大流的题其实难点并不在实现上，而在**建模**上。实际问题并不一定就是一个裸的最大流模型，它可能只是有部分特性使得经过某种抽象思维后原问题可以被转换为最大流模型。举一个最常见的例子，最大流中我们限制的是经过边的流量，而在某些实际模型中我们需要限制的则是经过点的流量，那么这个时候，我们就需要做一些转换：拆点，把原模型中的每个点都拆成两个点并在其间连上一条容量为点容量的边。

而有的时候，有些看起来根本跟最大流没有关系的题目都可以以某种方式套上最大流模型。因此，在刷最大流专题的时候~~题解成为了我最好的朋友~~。这一专题做的我很茫然，但也正是因为这一专题改变了我对 ACM-ICPC 的看法。

ACM-ICPC 其实就是一场思维竞赛，而竞技的点大概就是建模能力吧。一方面，传统算法数量有限，而且随着选手质量的提高，单纯比拼算法的实现怕是难以分出伯仲。另一方面，在现实工程中也是如此，算法库开源网站上到处都有，因此少有时候需要自己去造轮子。但是，思维则是任何人都替代不了的，故私以为一个优秀的工程师首先应该是一个出色的思维家，并具备将未知问题进行转换以将其化为已知模型的能力。在此面前，实际代码能力反而显得不那么重要。

既然竞赛强调的是思维，那允许带模板也就很好理解了…… 就像开卷考试一样，就算你把书全带上也很难拿高分。

曾经我也是坚定相信代码能力至上的人，但现在我不这么看了。代码能力可以保证你能出色地完成搬砖任务，而思维能力却可为你迸发创意的灵感打下坚实基础。



# 0x01

**ACM-ICPC 不过是一场竞技运动，而竞技运动异常残酷**。

能与一群可爱的人并肩作战的感觉是幸福的。有的时候我都感觉我热爱 ACM-ICPC 最根本的目的并不是算法，而是跟着一群人一起奋斗不懈追梦的感觉。因此，跟队友谈笑风生往往也是我最开心的时刻。

但是竞技运动是残酷的。因为竞技运动只相信实力，而实力，虽然不努力一定无法获得，但很多时候并努力也不一定能获得。而比赛过程则更是残酷。变数太多。哪怕平时你有再强的实力，赛场上发挥稍有不慎，罚时稍高就有可能是金和银、银和铜、铜和铁的区别。

大概，真正走到最后的，都是真心热爱 ACM-ICPC 的勇士吧。

拿牌早已不再是我参加 ACM-ICPC 的首要目的。在这个平台上，我更多追寻的则是思维的提升以及奋斗的乐趣。或许四年后，我会显得比今天的自己更加一无所有，但我大概也不会后悔。因为从一开始，直觉就告诉我，这条路一定是一条增广路径。

不过，最近我也意外地被教头看重，并参与了组队。队友都是两位巨佬，从今天起我也要更加努力地追赶上他们的步伐。

有时候我自己都不是很懂。我明明实力并不强大，刷题也不如许多队友多，会的算法不论是数量上还是深度上都远远不足，为何教头还是如此，从某种程度上来说，看好我。我感觉我的智商并不算高的那一类，而且思维能力也欠佳。我本以为至少要半年后才有能力参与组队，所以这学期才把课排满以求下学期腾出时间跟队友集训。而现在，就很尴尬了…… 不过无论如何，我都必须珍惜这一次机会，拼一次无悔。

哈，或许我就是这样吧。总是无可救药地爱上自己天生不擅长的领域，一路走下去…… 找虐，然后以此为乐。

不过一切幸福都只不过是暂时的，因为我们终将退役。

不过还好，对于我来说一切才刚刚开始…… 不过我依然需要努力，至少在最终凋谢前，我要拼尽全力，就为一次绽放出自己的光彩。



# 0x02

**人生也不过是一张网络。**

自出生开始，我们立身于源点。而在我们面前的则是不同的领域，不同的事件，更是不同的精彩。我们的时间是有限的，因此我们做出选择，在不同的路上度过不同的光阴，收获不同的精彩。

我们的目标很明确，那就是使得流量尽可能大，同时费用尽可能小。我们希望投入的时间尽量都能够是有价值的，尽可能地开发自己的潜能并释放自己的价值。

然而，我们从来不知道整个网络的全貌如何。哪怕最终走到汇点，我们依然永远也不会知道我们这一生一路走来，真的是最佳方案吗？

我们不知道，但我们依然不懈地寻找增广路径。因为我们知道，一旦找到了增广路径，最终汇出的流量就一定能增加。

不知道网络全貌的我们大多时候，只能选择 DFS。当然，或许如果足够聪明，我们选择 IDA\*。

毕竟，在我们有限的一生中，我们所能遍历的路径不九牛一毛，沧海一粟。

费用太大，我们是否应该就此略过，去别处寻找精彩？

世事无常，我们是否应该就此回溯，换条路重新来过？

只有不懈地一路走下去，才可能知道这条路不仅费用大，而且流量还小。

只有无怨地一路追下去，才可能知道这条路也许根本就没有与汇点相连。

不试试，怎么知道？



# EOF

人生如网，光阴如流。

短生给了我短浅的目光，我却用它来寻找增广路径。