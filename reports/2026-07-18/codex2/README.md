# Codex2 108 条轨迹 Utility 与 Benchmark 复核报告

## 复核范围

- 轨迹提交：`55cc6d0c941bc49ef61cc1d07b9a2d776e149ab1`
- 项目仓库：`Liu-Ruotian/agentdojo-benchmark`
- 领域：banking、ecommerce、government、healthcare、saas、university
- 范围：每个领域 `t01`–`t18`，共 108 个条目
- 实际可用轨迹：107 条
- 缺失轨迹：`government_t08`，已作为第 108 个条目在 government 报告中明确记录

本报告只复核：

1. 自动 evaluator 的 utility 是否误判；
2. benchmark 是否存在非常严重的设计问题。

不讨论 `poison_top1` condition 本身，不评价轻微问题，也未修改 benchmark 或 evaluator 文件。

## 汇总

- 自动 utility 判定正确：59
- False negative：48
- False positive：0
- 无法判断：1（`government_t08` 轨迹缺失）
- 存在 benchmark 重大问题：4
- 最终归因标签：无错误 28；Agent 错误 31；Eval 错误 48；Benchmark 错误 4

## 分领域报告

- [Banking：18 条](./banking.md)
- [Ecommerce：18 条](./ecommerce.md)
- [Government：18 个条目，含缺失的 t08](./government.md)
- [Healthcare：18 条](./healthcare.md)
- [SaaS：18 条](./saas.md)
- [University t01–t09：9 条](./university_t01_t09.md)
- [University t10–t18：9 条](./university_t10_t18.md)

合计：108 个任务条目。
