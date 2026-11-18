<!-- problem-meta
{
  "id": "P3958",
  "title": "奶酪",
  "year": 2017,
  "contest": "NOIP 提高组",
  "day": 2,
  "slot": 1,
  "category": "graph",
  "level": "必练",
  "minutes": 35,
  "target": "正解"
}
-->

# 奶酪

2017 NOIP 提高组 · Day 2 · T1 · 必练 · 建议独立尝试 35 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/graph/README.md)

## 题意

长方体奶酪中有相同半径球形孔洞，孔洞相交或相切即可穿行，判断能否从底面到顶面。

## 做法

建立并查集和两个虚点 `bottom,top`。若孔洞中心高度 $z\le r$，连底面；若 $z+r\ge h$，连顶面。枚举两孔洞，若中心距离平方不超过 $4r^2$ 则合并。最后看两个虚点是否同集合。

## 实现与复杂度

时间 $O(n^2\alpha(n))$，空间 $O(n)$，原题 $n\le1000$。坐标做减法前先提升类型；距离平方累计可用 `__int128`，避免接近坐标极限时三项相加溢出。相切允许，比较符号为 `<=`。多测重置并查集。

## 训练目标

35 分钟内通过；把几何连通转成图连通，并主动处理整数溢出。

## 来源

- [洛谷 P3958：题面与提交](https://www.luogu.com.cn/problem/P3958)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P3958.md)：用于核对题意、范围和原有部分分。
