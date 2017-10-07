---
title: 玩玩身份证
date: 2017-09-01 23:00:10
tags: 
- Identy Card
category: Notes
---

# 前言

最近边写[codgic-api](https://github.com/codgician/codgic-api)边啃大学教材好累啊…… 于是打算找点有意思的东西玩玩。

刚才在知乎上看到 **@刘巍然-学酥** 对于[身份证的末位校验码算法最后一步模11是基于什么考虑](https://www.zhihu.com/question/20205184)问题的回答后感觉颇有趣味，于是打算再深入理解理解身份证编号的那些事……

友情提示：此处身份证指的是中华人民共和国公民身份证，其它证件不在本文讨论范围之内。

友情提示*2：本文大部分是搬运的，别打我……



# 号码的结构

身份证号码（共18位）可以分为四个部分：

1. 地址码（6位）：公民常住户口所在县（市、镇、区）的行政区划代码。
2. 出生日期码（8位）：公历年、月、日；
3. 顺序码（3位）：给同地址码同出生日期码的人编订顺序号，**其中奇数分配给男性，偶数分配给女性**；
4. 校验码（1位）：采用**ISO 7064:1983,MOD 11-2**校验码系统。校验码为一位数字或X（校验码为10的情况）；

以身份证号 11010519491231002X 为例，地址码110105，也就是北京市朝阳区；出生日期码19491231，也就是该人出身于1949年12月31日；顺序码002；校验码X（也就是10）。



# 校验码的计算方法

1. 将身份证号从右至左排列一词标记为$a_1$, $a_2$, ... ,$a_{18}$，其中$a_1$就是校验码；
2. 分别计算出每一位的权重$W_i = 2^{i - 1} \ mod \  11$，得到：

| $i$  | 18   | 17   | 16   | 15   | 14   | 13   | 12   | 11   | 10   | 9    | 8    | 7    | 6    | 5    | 4    | 3    | 2    | 1    |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $Wi$ | 7    | 9    | 10   | 5    | 8    | 4    | 2    | 1    | 6    | 3    | 7    | 9    | 10   | 5    | 8    | 4    | 2    | 1    |

3. 计算：$S = \sum\limits_{i=2}^{18} a_i \cdot W_i$；
4. 校验码：$a_1 = (12 - (S \ mod \ 11)) \ mod \ 11$。




让人算好麻烦，顺手撸个校验验证码的程序吧（最近在复习C，大佬不要打我）：

``` c
#include "stdio.h"
#include "stdbool.h"
#include "string.h"
#include "math.h"

_Bool validateId(char id[18])
{
    int checksum, sum = 0;
    for (int i = 0; i < 17; i++)
    {
        sum += ((int)pow(2, 17 - i) % 11) * ((int)id[i] - 48);
    }
    checksum = (12 - (sum % 11)) % 11;
    return (int)id[17] == 88 ? checksum == 10 : checksum == (int)id[17] - 48; // 88 == "X"
}

int main()
{
    char id[18];
    scanf("%s", id);
    printf("%d", validateId(id));
    return 0;
}
```



# 为什么要这样设计？

**未完待续……**



# 参考文献

- [中华人民共和国公民身份号码 - Wikipedia](https://zh.wikipedia.org/wiki/%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E5%85%AC%E6%B0%91%E8%BA%AB%E4%BB%BD%E5%8F%B7%E7%A0%81)
- [身份证的末位校验码算法最后一步模11是基于什么考虑 - 刘巍然-学酥](https://www.zhihu.com/question/20205184)
