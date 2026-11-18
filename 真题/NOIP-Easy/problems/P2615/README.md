<!-- problem-meta
{
  "id": "P2615",
  "title": "神奇的幻方",
  "year": 2015,
  "contest": "NOIP 提高组",
  "day": 1,
  "slot": 1,
  "category": "simulation",
  "level": "必练",
  "minutes": 30,
  "target": "正解"
}
-->

# 神奇的幻方

2015 NOIP 提高组 · Day 1 · T1 · 必练 · 建议独立尝试 30 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/simulation/README.md)

## 题意

按给定规则在奇数阶 $n\times n$ 方阵中填写 $1\ldots n^2$。

## 做法

将 1 放在第一行中间列。之后每次先尝试“上一行、右一列”，行列越界分别循环回另一端；目标格空则放入，否则放在原位置正下方。统一用取模处理四类边界，避免为题面每一种情况重复写代码。

## 实现与复杂度

时间、空间均为 $O(n^2)$。下标从 0 开始时，候选位置为 `((r-1+n)%n,(c+1)%n)`，冲突时为 `((r+1)%n,c)`。填完后检查每行每列总和均为 $n(n^2+1)/2$；$n=1$ 必测。

## 训练目标

30 分钟内通过；把分支模拟改写成一个统一候选位置。

## 来源

- [洛谷 P2615：题面与提交](https://www.luogu.com.cn/problem/P2615)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P2615.md)：用于核对题意、范围和原有部分分。
