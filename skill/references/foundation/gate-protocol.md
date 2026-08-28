# 基座 #5 · Gate 文件协议

> 检查点的物化。来源:huashu 2.0,事故驱动——2026-07-17 跳过方向确认直接渲 210s 全片 → 整片视觉返工。**检查点容易在长会话里被「继续/开工/快点」的惯性冲掉,所以物化为文件:文件不在 = 环节没做。**

## 三个 Gate 文件

| Gate 文件 | 对应环节 | 什么时候必须有 |
|---|---|---|
| `brand-spec.md` | 品牌资产协议产物 | 涉及具体品牌/产品的任何设计 |
| `direction-approved.md` | 三方向展示 + **Ed 选择原话**记录(含三版初稿截图路径) | 实现开工前;≥45s 长片渲染前有 hook 硬检查 |
| `导演稿.md`(director's notes) | 长片/宣传片的分镜与视觉密度条款 | ≥20s 动画开工前(<20s 不强制导演稿但分镜卡照画;launch film 级升级为万字 notes) |

Gate 文件存放在**当前项目目录**,随项目走(设计 gate 文件留在所属项目 repo 内,不随意外发)。

## 核心规则

1. **任何授权语气不豁免**:「Ed 说继续」授权的是进入下一步,不是跳过该步内部的 gate。跳过必须 Ed 明说,且把「Ed 明示跳过 + 原话」写进对应 gate 文件
2. **没有「已有明确 design context」豁免通道**(上游 2026-07-18 实锤滥用后废止)——唯一合法豁免是 `direction-advisor.md` 的三种情形,且必须记录 Ed 原话/迭代来源
3. **弱 runtime 降级不豁免 gate 文件**——降级允许把检查点问答换成 assumption 清单,但三个 gate 文件照写(写文件不耗上下文),assumption 清单写进对应 gate 文件

## hook 硬拦

`scripts/design-gate-hook.sh`(Phase 2 迁入):≥45s 长片渲染前检查 `direction-approved.md` 是否存在——**缺文件 block 渲染**。Ed 明说跳过时用 `SKIP_DESIGN_GATE=1` 显式放行(留痕,不是默认)。

## direction-approved.md 模板

```markdown
# Direction Approved
- 日期:YYYY-MM-DD
- 展示了哪几版:[轮盘版/参照版/设计师版] + 截图路径
- Ed 选择原话:「……」
- 选定方向:[某版 / 混合:…… / 豁免:理由]
- 三拨盘读数:VARIANCE n / MOTION n / DENSITY n
```
