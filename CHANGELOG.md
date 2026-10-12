# CHANGELOG（编年体 · 只增不改，倒序）

> 格式：`YYYY-MM-DD ［类型］一句话（影响/依据）`；类型 = 新增/变更/修复/废弃/移除。
> 所有显著变更在此记一条；活态进度看 [TASK_STATUS.md](TASK_STATUS.md)，问题看 [ISSUES.md](ISSUES.md)。

## 2026-10-12

- ［修复］旁观者评审治理修正（本轮）：AGENTS 冷启动路径/§3 目录树/§5 命令全部对齐现行结构（旧 `docs/memory/`、`project-management/TASK_STATUS|ISSUES`、顶层 `knowledge-base/`、`concepts/` 已废）；WORKFLOW 旧路径改指 `projects/jewelry/...` 与根 `ISSUES.md`；memory/index ADR 链接改指 `docs/project-management/decisions/` 并补登珠宝线 ADR-003/004/005；TASK_STATUS/ISSUES 台账对齐 git 历史（朋友圈两线并存、ADR 范围 001~006）；README decisions 计数改 001~006；总纲 research-toolkit 括注更正为全局技能；出《旁观者评审报告_2026-10-12》。
- ［新增］ADR-006《泉泉方法论吸收范围与赛道取舍》（`db5ab14`）；运营方法库七件套 01~08 + D1-D7 按泉泉框架增强（`33e4a9f`）；泉泉方法论深度梳理 + 运营自动化与知识库融合方案（`5e49f77`）。
- ［变更］README 完整目录树重写（两条内容线 + deps 子模块 + 组织逻辑，`078ac03`）；DOCUMENTATION_MAP 按仓库根基准重写、补运营方法库/融合方案索引，README 补"文档边界"表，出质量检查报告（`19c7f1f`）。

## 2026-10-11

- ［变更］朋友圈 AI 工作台线三迁归位本仓：外部仓 `wechat-moments`（`5d50838`）→ 挂 deps 私有子模块（`89f7e29`）→ 并入本仓 `projects/wechat-moments/` 并移除子模块（`79f03b7`），与珠宝线两线并存；总纲补"五层体系 + 总控仓格局表"。

## 2026-10-09

- ［新增］挂载体系子模块聚合 `deps/`（用户拍板"直接用 submodule"）：trend-radar（③ 情报雷达）/ control-tower（总控）/ pipeline（① 采集底座）/ video-studio（④ 生产执行）以 git submodule 纳入本仓，实现驱动方单一工作区；`deps/README.md` 记录清单/使用/纪律（情报以最新为准 → 使用前 `submodule update --remote --merge`）。
- ［变更］指针同步：生产仓引用 `ai-video-studio → video-studio`（AGENTS/ISSUES/repo-map 三处）。

## 2026-10-08

- ［新增］治理三件套补全（本次）：新建根目录 `TASK_STATUS.md`（活态进度台账，唯一进度真相）、`ISSUES.md`（待验证/文档漂移/脚本与账号状态）、本 `CHANGELOG.md`。此前 README/AGENTS/DOCUMENTATION_MAP/WORKFLOW 多处引用 TASK_STATUS/ISSUES 但全仓不存在，本次补齐。
- ［修复］README 目录树与实际结构对齐：旧树仍写顶层 `knowledge-base/`、`project-management/`、`docs/research/`、`docs/AI内容调研/` 等，均已不存在；实际为框架留 `docs/`、珠宝内容落 `projects/jewelry/`。本次只改 README 目录树与相关路径描述，不动 projects/ 下既有内容。

## 2026-10-08（同日早段 · 结构重构）

> 依据 git log（`d5d8159` → `7404f14`）与文件 mtime。

- ［变更］建 `总纲.md` + 项目分层：跨项目框架留 `docs/`，珠宝具体内容整体落到 `projects/jewelry/`（knowledge-base/ research/ platforms/ archive/）。
- ［新增］治理档案：建 `docs/WORKFLOW.md`、`docs/REQUIREMENTS.md`、`docs/DOCUMENTATION_MAP.md`，补 `docs/project-management/standards/`（合规检查清单/不AI化质量标准/踩坑记录）与 `templates/每日脚本模板.md`。
- ［新增］ADR-003~005（均 2026-10-08 已确认）：珠宝项目人设（ADR-003）、不出镜不 AI 配音的内容形式（ADR-004）、三平台优先级视频号>小红书>抖音（ADR-005）。
- ［变更］调研目录合并：AI 内容调研并入 `projects/jewelry/research/`，去重 4 个旧文件；`research/线上优先/` 保留纯线上获客专题。
- ［变更］新建 `projects/jewelry/platforms/`（三平台执行），落 D1-D7 冷启动第一周包 + 第一周对标账号参考；`platforms/{shipinhao,xiaohongshu,douyin}/` 三个产出目录预建（待填）。
- ［变更］旧版方案归档：24 个历史执行方案 + 旧版 PDF/Word 移入 `projects/jewelry/archive/`（不删）。
- ［变更］朋友圈 AI 工作台系列迁出本仓，独立为 `pengyouquan` 仓（commit `5bdf6f9`）；本仓聚焦珠宝冷启动。
- ［变更］`docs/SYSTEM_STRATEGY.md` 重写挂五仓体系，明确当前只做珠宝冷启动、框架可复用。
- ［变更］仓名 `self-media-ops → we-media-ops`（`d31af1b`，英文原生词源同步，含 README/AGENTS/repo-map/调研报告路径）；调研渠道清单方法论说明改为 research-toolkit 技能（`8e98e45`）。
