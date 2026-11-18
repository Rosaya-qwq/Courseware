<!-- problem-meta
{
  "id": "P1328",
  "title": "生活大爆炸版石头剪刀布",
  "year": 2014,
  "contest": "NOIP 提高组",
  "day": 1,
  "slot": 1,
  "category": "simulation",
  "level": "必练",
  "minutes": 20,
  "target": "正解"
}
-->

# 生活大爆炸版石头剪刀布

2014 NOIP 提高组 · Day 1 · T1 · 必练 · 建议独立尝试 20 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/simulation/README.md)

## 题意

两人按各自周期出五种手势，模拟 $N$ 轮并统计胜场。

## 做法

将题目的胜负表直接写成 $5\times5$ 数组。第 $i$ 轮读取 $A_{i\bmod n_A}$ 和 $B_{i\bmod n_B}$，查表决定得分，平局双方都不加。

## 实现与复杂度

时间 $O(N)$，空间 $O(n_A+n_B)$。每个手势恰好胜两种、负两种，可据此检查表；再检查 `win[x][y]` 与 `win[y][x]` 相反，主对角线全为 0。

## 训练目标

20 分钟内通过；练习把复杂规则转换为静态表，而不是写大量条件分支。

## 来源

- [洛谷 P1328：题面与提交](https://www.luogu.com.cn/problem/P1328)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1328.md)：用于核对题意、范围和原有部分分。
