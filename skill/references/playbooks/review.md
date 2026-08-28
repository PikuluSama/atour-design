# Playbook · review(设计评审)

> 触发:「评审」「打分」「review this design」「好不好看」「帮我看看设计」
> 对任何设计产出(eds-design 自己的或外部的)做结构化评审。

## 流程

1. **读对象**:拿到要评审的 HTML/截图/URL。HTML 先 Playwright 截图 + 浏览真实渲染,不凭代码云评审
2. **走基座评审框架**:`foundation/review-5d.md`——维度 0 概念(一票否决)+ 维度 1-5 执行层
3. **场景侧重点**:按对象类型调权重(原型重功能性、封面重概念与层级、动画重节奏、信息图重传达)——详见 review-5d.md 场景表
4. **输出**:雷达图 + Keep / Fix / Quick Wins + 总评一句话定性
5. **Fix 项给修法**:每条问题定位到文件与区域,给出具体修改方向,不泛泛说「优化体验」

## 深度参考

- 完整评分细则与各维度检查清单 → `library/critique-guide.md`
- 评审时对照的工程底线 → `foundation/engineering-checklist.md`
- 反 slop 命中检查 → `foundation/anti-slop.md`

## 边界

- 评审不自动改稿——Ed 说「按评审修」才进 `polish.md`
- 评审外部设计(别人的作品)保持建设性语气,指出问题 + 给替代方案
