# ISSUES · 开放问题 / 待验证 / 阻塞项

> **文档类型**：Active（全局活态台账）
> **更新频率**：发现新问题或待验证项闭环时
> **维护者**：AI 自动维护
> **读者**：AI 代理（排障/动手前先查是否已知）+ 用户（看遗留风险）

## 职责边界

- 本文件装：跨阶段的待验证假设、文档/机制漂移、脚本与工具状态、账号合规风险。
- 进度在 [TASK_STATUS.md](TASK_STATUS.md)，编年变更在 [CHANGELOG.md](CHANGELOG.md)，本文件只记"问题/未决"本身。
- 只影响某一天脚本的临时问题，不提升到这里；共性结论解决后沉淀为 ADR/standards。

状态：`待验证` → `已核实✅ / 已排除❌ / 持续观察👀`。

---

## 一、待验证假设（来自 memory / 踩坑记录）

| ID | 项 | 状态 | 来源 / 备注 |
|----|----|------|------|
| I-001 | AI 生成珠宝视频的商业可用性：火彩/反光/佩戴比例不准，目前只适合氛围片、不适合产品展示 | 待验证 | [memory/index.md](docs/project-management/memory/index.md) + [standards/踩坑记录.md](docs/project-management/standards/踩坑记录.md)；对照 video-studio 三档流水线后拍板 |
| I-002 | 小红书封面具体配色方案：调研说避免大面积灰黑、需亮色调，但定稿配色未定 | 待验证 | memory 待验证 + 踩坑记录（"小红书封面不能用黑底"） |
| I-003 | 抖音内容是否需要真人出镜：与 ADR-004"不出镜"有张力，25-45 秒纯产品怼光片能否撑住抖音完播率待实测 | 待验证 | memory 待验证；ADR-004 已定不出镜，本条是效果侧待验证，不推翻决策 |

## 二、文档路径漂移（2026-10-08 结构重构后旧引用未改）

> 重构把知识库/research/archive 整体搬到 `projects/jewelry/`、治理档案落 `docs/project-management/`。下列旧路径已于 **2026-10-12 旁观者评审本轮全部修指闭环**。

| ID | 位置 | 问题 | 状态 |
|----|------|------|------|
| I-004 | [docs/WORKFLOW.md](docs/WORKFLOW.md) | 多处旧路径：`knowledge-base/...`、`docs/research/...`、`project-management/ISSUES.md` | ✅ 已修复（2026-10-12）：全部改指 `projects/jewelry/...` 与根 `ISSUES.md` |
| I-005 | [docs/project-management/memory/index.md](docs/project-management/memory/index.md) | 链接写 `docs/decisions/ADR-001...`，实际在 `docs/project-management/decisions/` | ✅ 已修复（2026-10-12）：改指 `docs/project-management/decisions/`，并补登珠宝线 ADR-003/004/005 |
| I-006 | [docs/DOCUMENTATION_MAP.md](docs/DOCUMENTATION_MAP.md)、[AGENTS.md](AGENTS.md) | 仍引用 `project-management/TASK_STATUS.md|ISSUES.md`、`docs/research/`、顶层 `knowledge-base/` 等旧路径 | ✅ 已修复：MAP 于 19c7f1f 重写；本轮 AGENTS 冷启动路径/目录树/命令全部对齐现行结构 |

## 三、脚本与工具状态

| ID | 项 | 状态 | 备注 |
|----|----|------|------|
| I-007 | `scripts/scan_xhs.js`（扫描）、`scripts/human_browse_xhs.js`（人味养号浏览） | 待核实 | 两脚本均 puppeteer-core attach 到本机已开 Chrome（读 `DevToolsActivePort`），依赖 Chrome 以远程调试模式启动；本仓无 package.json / scripts/README，"养号"是否已跑通待用户确认 |

## 四、账号与合规

| ID | 项 | 状态 | 备注 |
|----|----|------|------|
| I-008 | 新号冷启动前置：一机一号 + 手机流量 + 养号 2-3 天 | 待用户确认 | README 记录"账号曾被小红书警告过"，故严格走红线；新号是否已注册/开始养号待用户反馈 |

---

## 五、已解决（近期）

| ID | 问题 | 解决时间 | 结果 |
|----|------|----------|------|
| — | 配图路线不清（黑底卡到底给谁用） | 已闭环 | [standards/踩坑记录.md](docs/project-management/standards/踩坑记录.md) 标 [x]：朋友圈黑底卡、小红书明亮底、抖音举纸怼镜头 |
| — | 朋友圈 AI 工作台线与珠宝线人设混淆 | 已闭环 | 两线人设/语气/平台/目标完全分开（见 WORKFLOW 内容线表）；朋友圈线 2026-10-11 经三迁归位本仓 `projects/wechat-moments/`，与珠宝线并存、互不混写 |

---

## 维护规则

1. 发现新问题/新待验证项 → 在对应分区加一行，分配 ID（I-XXX）。
2. 闭环后移到"已解决"并记结果；文档漂移类修完即销项。
3. 进度类不进本文件，回 [TASK_STATUS.md](TASK_STATUS.md)。
