<!-- problem-meta
{
  "id": "P1969",
  "title": "积木大赛",
  "year": 2013,
  "contest": "NOIP 提高组",
  "day": 2,
  "slot": 1,
  "category": "greedy",
  "level": "必练",
  "minutes": 20,
  "target": "正解"
}
-->

# 积木大赛

2013 NOIP 提高组 · Day 2 · T1 · 必练 · 建议独立尝试 20 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/greedy/README.md)

## 题意

每次选一段当前高度都为正的连续积木，将整段高度减一，求全部清零的最少操作数。

## 做法

令 $a_0=0$，答案为 $\sum_{i=1}^n\max(0,a_i-a_{i-1})$。从左到右，已有操作最多延续覆盖到前一格的高度；新增加的高度必须新开操作，因此得到下界。将每层连续的正高度区间分别删除，恰好达到下界。

## 实现与复杂度

时间 $O(n)$，空间 $O(1)$。答案用 64 位。不要按最大高度逐层模拟，也不要反复找区间最小值造成平方复杂度。

## 训练目标

20 分钟内通过；和铺设道路一起说明差分正部的意义。

## 来源

- [洛谷 P1969：题面与提交](https://www.luogu.com.cn/problem/P1969)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1969.md)：用于核对题意、范围和原有部分分。
