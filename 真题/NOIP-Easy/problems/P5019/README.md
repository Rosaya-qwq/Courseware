<!-- problem-meta
{
  "id": "P5019",
  "title": "铺设道路",
  "year": 2018,
  "contest": "NOIP 提高组",
  "day": 1,
  "slot": 1,
  "category": "greedy",
  "level": "必练",
  "minutes": 15,
  "target": "正解"
}
-->

# 铺设道路

2018 NOIP 提高组 · Day 1 · T1 · 必练 · 建议独立尝试 15 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/greedy/README.md)

## 题意

每次选一段尚未填平的连续道路，使所有深度减一，求全部填平的最少天数。

## 做法

令 $d_0=0$，答案 $\sum_i\max(0,d_i-d_{i-1})$。在第 $i$ 格新增加的高度无法由覆盖前一格的操作承担，至少需要新开这些操作；每一层的连续区间分别填平即可实现。

## 实现与复杂度

时间 $O(n)$，空间 $O(1)$，总和用 64 位。不要按天模拟。和积木大赛是相同模型，可将本题用于隔天限时重写，检验是否真正掌握。

## 训练目标

15 分钟内通过，能在另一种背景下认出差分正部。

## 来源

- [洛谷 P5019：题面与提交](https://www.luogu.com.cn/problem/P5019)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P5019.md)：用于核对题意、范围和原有部分分。
