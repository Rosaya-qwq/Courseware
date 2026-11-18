<!-- problem-meta
{
  "id": "P2038",
  "title": "无线网络发射器选址",
  "year": 2014,
  "contest": "NOIP 提高组",
  "day": 2,
  "slot": 1,
  "category": "enumeration",
  "level": "必练",
  "minutes": 25,
  "target": "正解"
}
-->

# 无线网络发射器选址

2014 NOIP 提高组 · Day 2 · T1 · 必练 · 建议独立尝试 25 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/enumeration/README.md)

## 题意

在 $0\ldots128$ 的整数网格选发射器位置，覆盖切比雪夫距离不超过 $d$ 的点，最大化覆盖人数并统计最优位置数。

## 做法

枚举全部 $129^2$ 个发射器位置，对每个居民点判断 $|x-x_i|\le d$ 且 $|y-y_i|\le d$，累加人数，更新最大值和个数。范围很小，直接枚举足够。

## 实现与复杂度

时间 $O(129^2n)$，空间 $O(n)$。覆盖形状是正方形，不能用欧氏距离。最优值相等时累加方案数，更优时重置为 1；坐标 0 和 128 都要枚举。可选扩展：二维前缀和将每个位置求值降为 $O(1)$。

## 训练目标

25 分钟内通过；先估算枚举量，避免把小题写成复杂数据结构题。

## 来源

- [洛谷 P2038：题面与提交](https://www.luogu.com.cn/problem/P2038)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P2038.md)：用于核对题意、范围和原有部分分。
