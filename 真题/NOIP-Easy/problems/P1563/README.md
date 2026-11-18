<!-- problem-meta
{
  "id": "P1563",
  "title": "玩具谜题",
  "year": 2016,
  "contest": "NOIP 提高组",
  "day": 1,
  "slot": 1,
  "category": "simulation",
  "level": "必练",
  "minutes": 25,
  "target": "正解"
}
-->

# 玩具谜题

2016 NOIP 提高组 · Day 1 · T1 · 必练 · 建议独立尝试 25 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/simulation/README.md)

## 题意

一圈玩具各自面朝内或外，按“当前玩具的左/右手方向走若干步”的指令移动，输出最终玩具名字。

## 做法

先根据题目的编号方向固定一张四格方向表，分别列出“朝内/朝外 × 左/右”对应下标加还是减。每条指令读取移动前玩具的朝向，查表更新 `pos=(pos+delta+n)%n`；步数先对 $n$ 取模。

## 实现与复杂度

时间 $O(n+m)$，空间 $O(n)$。不要凭直觉混用顺时针、编号递增和左右；用题目示意图或样例验证表的四种情况。移动方向依赖出发位置的玩具，不是到达位置。

## 训练目标

25 分钟内通过；编码前先写方向表和取模公式。

## 来源

- [洛谷 P1563：题面与提交](https://www.luogu.com.cn/problem/P1563)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1563.md)：用于核对题意、范围和原有部分分。
