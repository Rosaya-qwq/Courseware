<!-- problem-meta
{
  "id": "P1313",
  "title": "计算系数",
  "year": 2011,
  "contest": "NOIP 提高组",
  "day": 2,
  "slot": 1,
  "category": "math",
  "level": "必练",
  "minutes": 25,
  "target": "正解"
}
-->

# 计算系数

2011 NOIP 提高组 · Day 2 · T1 · 必练 · 建议独立尝试 25 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/math/README.md)

## 题意

求 $(ax+by)^k$ 中 $x^ny^m$ 的系数，对 10007 取模。

## 做法

二项式定理给出系数 $\binom{k}{n}a^nb^m$，其中 $n+m=k$。用 Pascal 递推 $C[i][j]=C[i-1][j-1]+C[i-1][j]$ 算组合数，用快速幂算两项幂。

## 实现与复杂度

时间 $O(k^2+\log k)$，可滚动成 $O(k)$ 空间。滚动 Pascal 必须倒序更新下标。初始化 $C[0][0]=1$，指数为零时幂等于 1。每次乘法前转 64 位。

## 训练目标

25 分钟内通过，能写出组合意义，不把 $n,m$ 或 $a,b$ 的指数配反。

## 来源

- [洛谷 P1313：题面与提交](https://www.luogu.com.cn/problem/P1313)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1313.md)：用于核对题意、范围和原有部分分。
