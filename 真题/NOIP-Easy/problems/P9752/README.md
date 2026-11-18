<!-- problem-meta
{
  "id": "P9752",
  "title": "密码锁",
  "year": 2023,
  "contest": "CSP-S",
  "day": 0,
  "slot": 1,
  "category": "enumeration",
  "level": "必练",
  "minutes": 35,
  "target": "正解"
}
-->

# 密码锁

2023 CSP-S · T1 · 必练 · 建议独立尝试 35 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/enumeration/README.md)

## 题意

五位十进制密码锁被恰好做一次非零转动：转动一位，或同方向同幅度转动相邻两位。给出 $n\le8$ 个转动后的状态，求可能的原密码数量。

## 做法

直接枚举 $00000\ldots99999$。对每个观测，计算每一位相对候选的模 10 差值。合法当且仅当恰有一位差值非零，或者恰有相邻两位差值非零且这两个模 10 差值相同。候选必须与每个观测都合法。

也可从第一个观测反向枚举 $5\times9+4\times9=81$ 个原密码，再逐个验证其余观测，效率更高。相同密码去重后计数。

## 实现与复杂度

直接枚举 $O(10^5\cdot5n)$，空间 $O(n)$；反推候选 $O(81\cdot5n)$。始终按五位数组保存，前导零有效。转动必须非零，所以原密码本身不属于该观测的候选；相邻不包括首尾环绕。

## 训练目标

35 分钟内用直接枚举通过；若还有时间，再替换候选生成方式。

## 来源

- [洛谷 P9752：题面与提交](https://www.luogu.com.cn/problem/P9752)。
- [wwqwq：全密码枚举与合法性判断](https://www.luogu.com.cn/article/1y301o6p)（[公开存档](https://www.luogu.me/article/1y301o6p)）。
- [rainygame：81 个反向候选](https://www.luogu.com.cn/article/287l9p0s)（[公开存档](https://www.luogu.me/article/287l9p0s)）。
