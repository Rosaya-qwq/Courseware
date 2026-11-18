<!-- problem-meta
{
  "id": "P1079",
  "title": "Vigenère 密码",
  "year": 2012,
  "contest": "NOIP 提高组",
  "day": 1,
  "slot": 1,
  "category": "simulation",
  "level": "必练",
  "minutes": 20,
  "target": "正解"
}
-->

# Vigenère 密码

2012 NOIP 提高组 · Day 1 · T1 · 必练 · 建议独立尝试 20 分钟

[返回总目录](../../README.md) · [分类总结](../../categories/simulation/README.md)

## 题意

密钥循环使用，对英文字母进行模 26 的加密；已知密钥和密文，还原明文并保留密文的大小写。

## 做法

把密钥字母不区分大小写映射到 $[0,25]$。对于密文第 $i$ 位，先记下大小写，再将字母编号减去第 $i\bmod |key|$ 个密钥编号，计算 $(x-k+26)\bmod26$，最后按原大小写输出。

## 实现与复杂度

时间 $O(|S|+|key|)$，空间 $O(|key|)$。`A/a` 都对应 0。负数取模前先加 26；密钥循环和明文字母大小写是两件独立的事。

## 训练目标

20 分钟内通过；自测密钥比密文长、跨过 `A/a` 回绕、混合大小写。

## 来源

- [洛谷 P1079：题面与提交](https://www.luogu.com.cn/problem/P1079)。
- [题面存档](https://github.com/OldAntique110/Luogu-Problems/blob/main/problem/P1079.md)：用于核对题意、范围和原有部分分。
