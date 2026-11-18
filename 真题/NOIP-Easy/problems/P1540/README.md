<!-- problem-meta
{
  "id": "P1540",
  "title": "机器翻译",
  "year": 2010,
  "contest": "NOIP 提高组",
  "day": 0,
  "slot": 1,
  "category": "simulation",
  "level": "必练",
  "minutes": 20,
  "target": "正解"
}
-->

# 机器翻译

2010 NOIP 提高组 · T1 · 必练 · 建议独立尝试 20 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/simulation/README.md)

## 题意

容量为 $M$ 的词典按先进先出淘汰。翻译 $N$ 个单词，统计需要查外部词典的次数。

## 做法

队列记录进入词典的顺序，布尔数组或集合记录当前是否存在。命中时不改变队列；未命中时答案加一，若已满则删除队首，再插入新词。队列和成员标记必须同步。

## 实现与复杂度

时间 $O(N)$，空间 $O(M+V)$，$V$ 为值域；用集合可避免值域数组。容量为 1、连续重复、刚被淘汰的词再次出现都应自测。不要写成命中后移到队尾的 LRU。

## 训练目标

20 分钟内独立通过；能说明队列与 `in[]` 各自维护什么。

## 来源

- [洛谷 P1540：题面与提交](https://www.luogu.com.cn/problem/P1540)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1540.md)：用于核对题意、范围和原有部分分。
