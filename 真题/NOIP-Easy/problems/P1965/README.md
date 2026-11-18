<!-- problem-meta
{
  "id": "P1965",
  "title": "转圈游戏",
  "year": 2013,
  "contest": "NOIP 提高组",
  "day": 1,
  "slot": 1,
  "category": "math",
  "level": "必练",
  "minutes": 15,
  "target": "正解"
}
-->

# 转圈游戏

2013 NOIP 提高组 · Day 1 · T1 · 必练 · 建议独立尝试 15 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/math/README.md)

## 题意

$n$ 个人编号 $0\ldots n-1$，从 $x$ 开始每次前进 $m$ 个位置，共进行 $10^k$ 次，求终点。

## 做法

答案为 $(x+m(10^k\bmod n))\bmod n$。用模快速幂计算 $10^k\bmod n$，不实际生成 $10^k$，也不循环 $10^k$ 次。

## 实现与复杂度

时间 $O(\log k)$，空间 $O(1)$。乘法先转 64 位；$k=0$ 时次数为 1。编号从 0 开始，公式中不需要额外加减 1。

## 训练目标

15 分钟内通过；能把重复移动转成模运算。

## 来源

- [洛谷 P1965：题面与提交](https://www.luogu.com.cn/problem/P1965)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1965.md)：用于核对题意、范围和原有部分分。
