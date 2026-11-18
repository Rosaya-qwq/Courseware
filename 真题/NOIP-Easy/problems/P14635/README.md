<!-- problem-meta
{
  "id": "P14635",
  "title": "糖果店",
  "year": 2025,
  "contest": "NOIP",
  "day": 0,
  "slot": 1,
  "category": "greedy",
  "level": "必练",
  "minutes": 45,
  "target": "正解"
}
-->

# 糖果店

2025 NOIP · T1 · 必练 · 建议独立尝试 45 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/greedy/README.md)

## 题意

第 $i$ 种糖果库存无限，购买这一种时单颗价格交替为 $x_i,y_i,x_i,y_i,\ldots$，给定预算 $m$，最大化糖果总数。

## 做法

每种购买数量唯一分成若干对加至多一个单颗：一对花费 $x_i+y_i$，余下单颗花 $x_i$。成对购买全部改用最便宜的一种即可，设一对最小价格为 $p=\min_i(x_i+y_i)$。

单颗部分每种至多一颗，选恰好 $t$ 种时，取 $x_i$ 最小的 $t$ 个，前缀花费为 $S_t$。剩余钱买尽量多对，枚举 $t=0\ldots n$ 且 $S_t\le m$，答案为

$$\max_t\left(t+2\left\lfloor\frac{m-S_t}{p}\right\rfloor\right).$$

最便宜成对糖果同时出现在单颗部分也合法：它相当于先买若干对，再多买奇数位的一颗。

## 实现与复杂度

时间 $O(n\log n)$，空间 $O(n)$。前缀和、预算、答案用 64 位或更宽中间类型。前缀超过预算后即可停止；包含 $t=0$。不能只先把成对糖果买到不能买再用余钱买单颗，这样会漏掉“少买一对换更多种单颗”。

## 训练目标

45 分钟内通过；学会把无限交替价格分成“重复的整对”和“有限的余项”。

## 来源

- [洛谷 P14635：题面与提交](https://www.luogu.com.cn/problem/P14635)。
- [pies_0x：单颗与成对购买的拆分](https://www.luogu.com.cn/article/z8t1itgn)（[公开存档](https://www.luogu.me/article/z8t1itgn)）。
