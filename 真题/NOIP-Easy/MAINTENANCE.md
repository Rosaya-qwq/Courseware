# 更新方法

[返回总目录](README.md)

每题放在 `problems/P题号/README.md`，题解只维护这一份；总目录、按年目录和分类页中的题目表均自动生成。分类页前面的通用思路、七天安排与其他说明是人工正文，刷新不会改写。

## 新增一道题

1. 新建 `problems/Pxxxxx/README.md`，参考下方模板。
2. 填写开头的 `problem-meta` 元信息，`category` 选已有知识点，`target` 明确写本周正解或具体部分分条件。
3. 写题意、做法、实现复杂度与训练目标；T2 必须写“关键部分分”。来源应链接实际阅读过的原题或文章。
4. 在本目录运行 `python tools/refresh.py`。
5. 运行 `python tools/refresh.py --check`，检查目录是否已更新、历年范围是否完整、本地链接是否失效。

新增题不必编辑多份目录，也不需要修改生成器里的历史题号清单。比赛题的 `(year, contest, day, slot)` 必须唯一。普通补充练习可填写 `year=0, contest="补充练习", day=0, slot=0`，仍按知识点进入总目录和分类页，不混入历年 T1/T2 核对表；补充练习不限数量。

## 单题模板

元信息采用标准 JSON，不需要安装第三方库。`day=0` 表示单日赛，双日赛分别填 1、2；`slot=0` 表示补充练习，1、2 表示原卷题号。`minutes` 为建议独立尝试上限，`level` 为“必练”“提高”或“拓展”。

```markdown
<!-- problem-meta
{
  "id": "Pxxxxx",
  "title": "中文题名",
  "year": 2026,
  "contest": "NOIP",
  "day": 0,
  "slot": 2,
  "category": "dp",
  "level": "提高",
  "minutes": 60,
  "target": "先做 n≤20 的子集枚举，再做完整 DP"
}
-->

# 中文题名

[返回总目录](../../README.md) · [分类总结](../../categories/dp/README.md)

## 题意

准确概括目标、规模与必要规则。

## 关键部分分

条件 → 算法／转移 → 复杂度。T1 可省本节，T2 必须有。

## 做法

性质及理由、状态与初值、转移顺序、答案。

## 实现与复杂度

时间、空间、整数范围和影响正确性的边界。

## 训练目标

本次独立完成哪一档。

## 来源

原题链接和实际阅读过的参考资料。
```

## 分类标识

| category | 分类 |
| --- | --- |
| simulation | 模拟与规则实现 |
| enumeration | 枚举与缩小候选 |
| greedy | 贪心、排序与交换论证 |
| prefix-binary | 前缀统计、差分与二分 |
| dp | 动态规划与状态设计 |
| graph | 图的建模、遍历与连通 |
| tree | 树上计数、路径与回溯 |
| math | 数学、位运算与组合计数 |
| strings | 字符串、奇偶与状态编号 |
| construction | 构造与不变量 |

新增分类时，先创建对应 `categories/标识/README.md` 并写通用总结，保留 `BEGIN PROBLEMS` / `END PROBLEMS` 注释标记，再将分类加入 `tools/refresh.py` 的 `CATEGORIES`。请勿删除现有类别，除非已先迁移其中题目。

## 生成与本地维护

`refresh.py` 只替换带 `BEGIN` / `END` 标记的区域；请勿在这些区域手工修改表格。`--check` 为只读检查，失败会显示具体文件或缺项。七天计划不会随分类刷新而重排，新增题后由教师决定是否替换训练题。

本目录是 Markdown 训练库，直接打开 README 即可浏览。按 Courseware 的维护约定，公开提交保留文档；`tools/` 中的 Python 维护工具及本地核验脚本留在本机，不作为公开课件源码上传。换机器维护时应同时备份本地工具。
