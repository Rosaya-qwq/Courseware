<!-- problem-meta
{
  "id": "P11231",
  "title": "决斗",
  "year": 2024,
  "contest": "CSP-S",
  "day": 0,
  "slot": 1,
  "category": "greedy",
  "level": "必练",
  "minutes": 25,
  "target": "正解"
}
-->

# 决斗

2024 CSP-S · T1 · 必练 · 建议独立尝试 25 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/greedy/README.md)

## 题意

怪物具有能力值，每只怪物最多使用一次能力消灭一个能力值严格更小的怪物，安排操作使最终剩余怪物最少。

## 做法

能力值升序分组。设此前尚存 $live$ 只，新组有 $c$ 只，新组的每只可以消灭此前的一只，且本组不能互相消灭，所以

$$live=\max(0,live-c)+c=\max(live,c).$$

这样做不会妨碍后面的更大能力值怪物：新加入的怪物全部存活并且已用过能力，之后仍可作为被消灭对象；旧组未被消灭的怪物也不再需要施放能力。因此最终恰为某个相同能力值的最大出现次数。

## 实现与复杂度

排序后统计每个值的最大频次，时间 $O(n\log n)$，空间 $O(n)$；值域小可用桶。题面限制为严格更小，相等不能互杀。无需真的模拟每次配对。

## 训练目标

25 分钟内通过；从分组模拟推到最大频次公式，并说明相等值为什么要一起处理。

## 来源

- [洛谷 P11231：题面与提交](https://www.luogu.com.cn/problem/P11231)。
- [SunJude：按能力分组的贪心](https://www.luogu.com.cn/article/ybgq1cwt)（[公开存档](https://www.luogu.me/article/ybgq1cwt)）。
