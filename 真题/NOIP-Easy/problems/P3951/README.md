<!-- problem-meta
{
  "id": "P3951",
  "title": "小凯的疑惑",
  "year": 2017,
  "contest": "NOIP 提高组",
  "day": 1,
  "slot": 1,
  "category": "math",
  "level": "必练",
  "minutes": 25,
  "target": "正解"
}
-->

# 小凯的疑惑

2017 NOIP 提高组 · Day 1 · T1 · 必练 · 建议独立尝试 25 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/math/README.md)

## 题意

互质正整数 $a,b$ 可无限次使用，求不能表示为 $ax+by$（$x,y\ge0$）的最大整数。

## 做法

答案为 $ab-a-b$。先证它不可表示：若 $ab-a-b=ax+by$，则 $a(x+1)=b(a-y-1)$，互质性使 $x+1\ge b$，与右侧系数的范围矛盾。

再证更大的 $N$ 可表示：在 $0,b,2b,\ldots,(a-1)b$ 中，各模 $a$ 的余数恰一次，取与 $N$ 同余的一项 $yb$。若 $N-yb<0$，它是负的 $a$ 的倍数，故 $N\le yb-a\le(a-1)b-a=ab-a-b$，矛盾。因此剩余为非负的 $a$ 的倍数。

## 实现与复杂度

时间、空间均为 $O(1)$，计算乘积前转 64 位。结论使用互质条件；若扩展到非互质，不能表示的数无上界。不要只输出背下的公式却说不出条件。

## 训练目标

25 分钟内完成公式和证明；用小范围完全背包验证若干互质数对。

## 来源

- [洛谷 P3951：题面与提交](https://www.luogu.com.cn/problem/P3951)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P3951.md)：用于核对题意、范围和原有部分分。
