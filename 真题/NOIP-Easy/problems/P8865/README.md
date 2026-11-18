<!-- problem-meta
{
  "id": "P8865",
  "title": "种花",
  "year": 2022,
  "contest": "NOIP",
  "day": 0,
  "slot": 1,
  "category": "prefix-binary",
  "level": "提高",
  "minutes": 60,
  "target": "正解选做；基础班先看讲解或小规模实现"
}
-->

# 种花

2022 NOIP · T1 · 提高 · 建议独立尝试 60 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/prefix-binary/README.md)

## 题意

在无坑位置构造向右开口的 C、F 图案，两条横线之间至少隔一行，横线长度均至少 2，F 的竖线还需在下横线下方至少延伸一格。

## 做法

预处理 $R[i][j]$ 为从 $(i,j)$ 向右连续无坑、**不含自身**的格数，$D[i][j]$ 为其下方连续无坑、同样不含自身的格数。若两条横线位于 $x<i-1$，同列 $j$ 的贡献为 $R[x][j]R[i][j]$；若竖线继续向下，F 再乘 $D[i][j]$。

逐列扫描每段连续无坑行，维护上横线权值之和 $S$。到下横线行 $i$ 时，先把 $R[i-2][j]$ 纳入 $S$（仅当它仍在当前连续段中），再加

$$C\mathrel{+}=S\cdot R[i][j],\quad F\mathrel{+}=S\cdot R[i][j]\cdot D[i][j].$$

遇到坑立刻清空 $S$ 并重置连续段起点。最后按输入 $c,f$ 分别乘系数，模 998244353。

## 实现与复杂度

时间、空间均为 $O(nm)$，原题 $n,m\le1000$。最容易错的是把相邻两行作为两横，或把横线自身也算进 $R$。两横长度独立，不要求相同；F 向下延伸的每种终点都计为不同方案。

## 训练目标

先枚举上下两横，得到 $O(n^2m)$ 程序，再用逐列累计消掉一层循环。

## 来源

- [洛谷 P8865：题面与提交](https://www.luogu.com.cn/problem/P8865)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P8865.md)：用于核对题意、范围和原有部分分。
