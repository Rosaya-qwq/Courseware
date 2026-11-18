<!-- problem-meta
{
  "id": "P5664",
  "title": "Emiya 家今天的饭",
  "year": 2019,
  "contest": "CSP-S",
  "day": 2,
  "slot": 1,
  "category": "dp",
  "level": "提高",
  "minutes": 65,
  "target": "正解选做；基础班先看讲解或小规模实现"
}
-->

# Emiya 家今天的饭

2019 CSP-S · Day 2 · T1 · 提高 · 建议独立尝试 65 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/dp/README.md)

## 题意

每种烹饪方法至多选一道菜，食材 $j$、方法 $i$ 有 $a_{ij}$ 道可选。要求至少选一道，并且任一食材的数量均不超过所选总数的一半，求方案数。

## 做法

令 $s_i=\sum_j a_{ij}$，全部非空方案数为 $\prod_i(1+s_i)-1$。不合法方案中至多有一种食材占严格多数，因此可逐种食材计算违规方案并直接相减，不会重复扣除。

固定违规食材 $j$，令 $dp[d]$ 表示已处理方法中“选食材 $j$ 的菜数减其他菜数”为 $d$ 的加权方案数，$dp[0]=1$。对方法 $i$，选择不做、做食材 $j$、做其他食材，分别为

$$ndp[d]\mathrel{+}=dp[d],\quad ndp[d+1]\mathrel{+}=dp[d]a_{ij},\quad ndp[d-1]\mathrel{+}=dp[d](s_i-a_{ij}).$$

处理完后把所有 $d>0$ 的状态相加，便是该食材违规的方案数。

## 实现与复杂度

时间 $O(mn^2)$，空间 $O(n+m)$（可逐行读入保存矩阵时为 $O(nm)$），原题 $n\le100,m\le2000$；通常直接保存矩阵。差值下标偏移 $n$，逐层清空，模数 $998244353$。全部方案先减掉空方案，再减严格多数，不能把恰好一半扣除。

## 训练目标

较难 T1；本周理解“违规事件互斥”与差值 DP，能力不足时安排为讲解题。

## 来源

- [洛谷 P5664：题面与提交](https://www.luogu.com.cn/problem/P5664)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P5664.md)：用于核对题意、范围和原有部分分。
