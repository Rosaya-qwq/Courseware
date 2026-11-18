<!-- problem-meta
{
  "id": "P14362",
  "title": "道路修复",
  "year": 2025,
  "contest": "CSP-S",
  "day": 0,
  "slot": 2,
  "category": "graph",
  "level": "提高",
  "minutes": 75,
  "target": "优先小 k 全边 Kruskal、k=0；MST 压边选做"
}
-->

# 道路修复

2025 CSP-S · T2 · 提高 · 建议独立尝试 75 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/graph/README.md)

## 题意

已有 $n$ 座城市和 $m$ 条道路，可选择若干乡镇城市化。选乡镇需付固定费用，并可建设其到各城市的道路。使所有城市与被选乡镇连通，最小化总费用，$k\le10$。

## 关键部分分

- $k=0$：直接求原城市图的最小生成树，$O(m\log m)$。
- $k$ 小、$n,m$ 小：枚举 $2^k$ 个乡镇子集，每次重建全部边并排序跑 Kruskal，时间 $O(2^k(m+kn)\log(m+kn))$。计算所选乡镇的固定费，不能漏掉它。
- 先保留原图的一棵 MST，再对每个子集单独排序，降为 $O(m\log m+2^kkn\log(kn))$。这是有正确性依据的中间档，不用冒险写随机贪心。

## 做法

先在原城市图上求一棵 MST $T$，只保留其 $n-1$ 条边。再加入所有 $kn$ 条候选乡镇—城市边，一次性按权排序。枚举子集，跳过未选乡镇的边，重置并查集跑 Kruskal，累计所选固定费，取最小值。

为何可删原图非树边？对任一被删边 $e=(u,v)$，$T$ 中 $u\to v$ 路径每条边权均不大于 $w_e$。即使后来加入乡镇边，若某棵最优树用了 $e$，删去它形成一个割，原树路径必有一条边跨割且不更贵，可交换替换。故总存在只用 $T$ 的原城市边的最优解。**同权边可能属于其他 MST，并不意味着它们永远不可能被选**，正确论断是保留一棵 MST 已足够。

## 实现与复杂度

时间 $O(m\log m+kn\log(kn)+2^kkn\alpha(n+k))$，空间 $O(m+kn+n+k)$。要枚举空集；选了 $s$ 个乡镇的图需要 $n+s-1$ 次成功合并。总费用用 64 位。

## 训练目标

本周先完成枚举子集加原始 Kruskal；再学习如何用 MST 压缩候选边和避免重复排序。

## 来源

- [洛谷 P14362：题面与提交](https://www.luogu.com.cn/problem/P14362)。
- [Re_FYCCCCTA：逐步优化 Kruskal](https://www.luogu.com.cn/article/vbeotraz)（[公开存档](https://www.luogu.me/article/vbeotraz)）。
- [Just_Starlet：原图边压缩，本文修正同权边证明](https://www.luogu.com.cn/article/a97x5owm)（[公开存档](https://www.luogu.me/article/a97x5owm)）。
