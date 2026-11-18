<!-- problem-meta
{
  "id": "P1082",
  "title": "同余方程",
  "year": 2012,
  "contest": "NOIP 提高组",
  "day": 2,
  "slot": 1,
  "category": "math",
  "level": "必练",
  "minutes": 30,
  "target": "正解"
}
-->

# 同余方程

2012 NOIP 提高组 · Day 2 · T1 · 必练 · 建议独立尝试 30 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/math/README.md)

## 题意

求 $ax\equiv1\pmod b$ 的最小正整数解，原题保证 $a,b$ 互质。

## 做法

扩展欧几里得求 $ax+by=\gcd(a,b)=1$。递归返回 $bx'+(a\bmod b)y'=g$ 时，令 $x=y'$，$y=x'-\lfloor a/b\rfloor y'$。将结果规范为 $(x\bmod b+b)\bmod b$；本题 $b\ge2$ 时结果非零。

## 实现与复杂度

时间 $O(\log\min(a,b))$，递归空间同阶，中间运算用 64 位。模数未必为质数，不能直接用费马小定理。

## 训练目标

30 分钟内通过，能从递归方程推回系数，避免只背模板。

## 来源

- [洛谷 P1082：题面与提交](https://www.luogu.com.cn/problem/P1082)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1082.md)：用于核对题意、范围和原有部分分。
