<!-- problem-meta
{
  "id": "P5657",
  "title": "格雷码",
  "year": 2019,
  "contest": "CSP-S",
  "day": 1,
  "slot": 1,
  "category": "math",
  "level": "必练",
  "minutes": 25,
  "target": "正解"
}
-->

# 格雷码

2019 CSP-S · Day 1 · T1 · 必练 · 建议独立尝试 25 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/math/README.md)

## 题意

求递归反射构造的 $n$ 位格雷码中下标为 $k$ 的编码，下标从 0 开始，$n\le64$。

## 做法

二进制反射格雷码公式为 $g=k\oplus(k\gg1)$。设 $k$ 的二进制位为 $b_i$，则 $g_i=b_{i+1}\oplus b_i$，最高位前补 0。这个变换恰好使后一半编码倒序并在前面加 1，符合递归定义。

## 实现与复杂度

从 $n-1$ 到 0 输出 $g$ 各位，前导零不能省。时间 $O(n)$，空间 $O(1)$。$k$ 可能超过有符号 64 位上界，使用 `unsigned long long`；不要计算 `1ULL<<64`。

## 训练目标

25 分钟内通过；用 $n=2,3$ 手写结果理解反射构造。

## 来源

- [洛谷 P5657：题面与提交](https://www.luogu.com.cn/problem/P5657)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P5657.md)：用于核对题意、范围和原有部分分。
