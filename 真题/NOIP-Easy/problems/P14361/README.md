<!-- problem-meta
{
  "id": "P14361",
  "title": "社团招新",
  "year": 2025,
  "contest": "CSP-S",
  "day": 0,
  "slot": 1,
  "category": "greedy",
  "level": "必练",
  "minutes": 40,
  "target": "正解"
}
-->

# 社团招新

2025 CSP-S · T1 · 必练 · 建议独立尝试 40 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/greedy/README.md)

## 题意

把 $n$ 名成员分到三个部门，每人对三个部门有不同满意度，每个部门人数不超过 $\lfloor n/2\rfloor$，求最大总满意度。

## 做法

先让每人选择满意度最大的部门，求总分。若没有部门超额，这已达到逐人上界，直接输出。由于上限为半数，至多一个部门超额。

设超额部门为 $d$、人数为 $c$，需要转出 $r=c-\lfloor n/2\rfloor$ 人。对该部门成员计算转去其他部门的最小损失

$$loss_i=a_{i,d}-\max_{j\ne d}a_{i,j}.$$

选择损失最小的 $r$ 人转走，从总分中减去这些损失。其他任一部门原人数最多为 $n-c$，即使全部 $r$ 人都转入它，人数至多为 $n-\lfloor n/2\rfloor$；原题 $n$ 为偶数时恰为 $n/2$，因此不会产生新的超额。

## 实现与复杂度

时间 $O(n\log n)$，空间 $O(n)$。满意度相同任选一个最大部门即可；损失按另一边的最大满意度计算，不能固定把人全部转到某个指定部门。上述容量证明使用原题偶数 $n$ 的条件，不能把它无条件推广到奇数 $n$。

## 训练目标

40 分钟内通过；从无约束上界出发，只修正唯一超额部门。

## 来源

- [洛谷 P14361：题面与提交](https://www.luogu.com.cn/problem/P14361)。
- [DeepslateQAQ：超额部门与最小损失修正](https://www.luogu.com.cn/article/70szsxdl)（[公开存档](https://www.luogu.me/article/70szsxdl)）。
- [ftzx：贪心分组](https://www.luogu.com.cn/article/18s91dzq)（[公开存档](https://www.luogu.me/article/18s91dzq)）。
