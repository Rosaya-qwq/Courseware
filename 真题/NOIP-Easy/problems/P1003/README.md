<!-- problem-meta
{
  "id": "P1003",
  "title": "铺地毯",
  "year": 2011,
  "contest": "NOIP 提高组",
  "day": 1,
  "slot": 1,
  "category": "enumeration",
  "level": "必练",
  "minutes": 15,
  "target": "正解"
}
-->

# 铺地毯

2011 NOIP 提高组 · Day 1 · T1 · 必练 · 建议独立尝试 15 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/enumeration/README.md)

## 题意

按顺序铺矩形地毯，求最后覆盖给定点的地毯编号。

## 做法

倒序检查矩形，找到第一个覆盖点的矩形立即输出编号；全部不覆盖则输出 $-1$。覆盖条件为 $a\le x\le a+g$ 且 $b\le y\le b+k$，边界也算覆盖。

## 实现与复杂度

时间 $O(n)$，空间 $O(n)$。也可正序读入并不断更新答案。不要枚举平面上的所有格子。用“后铺的覆盖先铺的”证明倒序第一次命中就是答案。

## 训练目标

15 分钟内通过，主动检查矩形边界与完全不覆盖。

## 来源

- [洛谷 P1003：题面与提交](https://www.luogu.com.cn/problem/P1003)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1003.md)：用于核对题意、范围和原有部分分。
