<!-- problem-meta
{
  "id": "P2822",
  "title": "组合数问题",
  "year": 2016,
  "contest": "NOIP 提高组",
  "day": 2,
  "slot": 1,
  "category": "math",
  "level": "必练",
  "minutes": 35,
  "target": "正解"
}
-->

# 组合数问题

2016 NOIP 提高组 · Day 2 · T1 · 必练 · 建议独立尝试 35 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/math/README.md)

## 题意

固定 $k$，多次询问满足 $0\le j\le\min(i,m)$、$0\le i\le n$ 且 $k\mid\binom ij$ 的数对数量。

## 做法

Pascal 递推只保存 $C(i,j)\bmod k$。对三角区域中余数为 0 的位置设标记 1，再做二维前缀和。每次查询前缀矩形 $[0,n]\times[0,m]$ 的标记总和；$m>n$ 时可以截为 $n$。

## 实现与复杂度

设最大询问参数为 $N$，时间 $O(N^2+T)$，空间 $O(N^2)$，原题 $N\le2000$。三角形外的数组虽默认为 0，却不是组合数，**不能标记为可整除**。原题 $k\ge2$，$j=0$ 的组合数为 1，不贡献。

## 训练目标

35 分钟内通过；区分“合法状态值为零”和“非法数组位置初始化为零”。

## 来源

- [洛谷 P2822：题面与提交](https://www.luogu.com.cn/problem/P2822)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P2822.md)：用于核对题意、范围和原有部分分。
