<!-- problem-meta
{
  "id": "P1970",
  "title": "花匠",
  "year": 2013,
  "contest": "NOIP 提高组",
  "day": 2,
  "slot": 2,
  "category": "greedy",
  "level": "必练",
  "minutes": 40,
  "target": "先做 n≤1000 的二次方 DP，再做双状态正解"
}
-->

# 花匠

2013 NOIP 提高组 · Day 2 · T2 · 必练 · 建议独立尝试 40 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/greedy/README.md)

## 题意

从高度序列中选最长子序列，使相邻差的正负严格交替，起步方向任意。

## 关键部分分

- $n\le10$：枚举子集、检查高度差，$O(n2^n)$，对应原题 20% 范围。
- $n\le1000$：$up_i=1+\max_{j<i,h_j<h_i}down_j$，$down_i=1+\max_{j<i,h_j>h_i}up_j$，无前驱时为 1。$O(n^2)$，对应原题 70% 范围。

## 做法

连续相等高度不改变趋势，先忽略。保留首点，每当严格上升、下降趋势发生切换，保留此前的峰或谷，最后保留末点。等价地维护 `up,down`，初始均为 1：若 $h_i>h_{i-1}$，令 `up=down+1`；若小于则 `down=up+1`；相等不更新。

一段单调区间内最多需要一个端点，保留更高的峰或更低的谷只会扩大下一段的选择范围，所以保留极值不劣。

## 实现与复杂度

时间 $O(n)$，空间 $O(1)$。全相等答案为 1，严格单调且长度大于 1 时答案为 2。不能把等高当作转折。

## 训练目标

能先推二次方 DP，再解释为何可压缩成两个数。

## 来源

- [洛谷 P1970：题面与提交](https://www.luogu.com.cn/problem/P1970)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1970.md)：用于核对题意、范围和原有部分分。
