<!-- problem-meta
{
  "id": "P9868",
  "title": "词典",
  "year": 2023,
  "contest": "NOIP",
  "day": 0,
  "slot": 1,
  "category": "strings",
  "level": "必练",
  "minutes": 30,
  "target": "正解"
}
-->

# 词典

2023 NOIP · T1 · 必练 · 建议独立尝试 30 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/strings/README.md)

## 题意

每个单词的字母可任意重排。对每个单词 $i$，判断能否把它排得严格小于所有其他重排后的单词。

## 做法

把第 $i$ 个单词升序排成 $L_i$，其他单词降序排成 $R_j$。答案为 1 当且仅当 $L_i<R_j$ 对所有 $j\ne i$ 成立。这是每个单词分别达到的最优方向，互不冲突。

所有单词长度相同，因此只需记最小字符 $lo_i$ 和最大字符 $hi_i$，条件进一步简化为 $lo_i<hi_j$。若首字符相等为 $c$，则 $L_i$ 所有字符都不小于 $c$，而 $R_j$ 所有字符都不大于 $c$，不可能严格更小。

实现可用 $O(n^2)$ 比较所有单词，原题规模足够；也可维护 $hi$ 的最小值、出现次数和次小值，排除自身后 $O(1)$ 判断。

## 实现与复杂度

直接版本 $O(nm+n^2)$，空间 $O(n)$；优化版 $O(nm+n)$。$n=1$ 时不存在其他单词，答案为 1。严格小于不能写成小于等于，单词全为同一字母时尤其要检查。

## 训练目标

30 分钟内通过；先证明升降序重排，再考虑是否真需要保存完整字符串。

## 来源

- [洛谷 P9868：题面与提交](https://www.luogu.com.cn/problem/P9868)。
- [xuan_gong_dong：首字符比较的化简](https://www.luogu.com.cn/article/p4jkeasb)（[公开存档](https://www.luogu.me/article/p4jkeasb)）。
