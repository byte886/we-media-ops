# TASK_STATUS · 进度台账（活态 · 唯一进度真相）

> **文档类型**：Active（全局活态台账）
> **更新频率**：阶段切换、里程碑完成、下一步变化时
> **维护者**：AI 自动维护
> **读者**：AI 代理（冷启动/接手先读）+ 用户（看全局进度）

## 职责边界

- 本文件只放：跨阶段里程碑状态、当前主线的指针级状态、全局下一步。回答"**本仓到哪了、接下来干什么**"。
- 不抄易变计数（具体脚本条数/素材个数/调研篇数以对应权威文件为准）。
- 问题/坑/待验证登记在 [ISSUES.md](ISSUES.md)；编年变更记在 [CHANGELOG.md](CHANGELOG.md)；本文件只做指针。
- 冷启动/续接必读顺序见 [AGENTS.md](AGENTS.md) §2。

> 最后更新：**2026-10-12（本轮治理修正：AGENTS/WORKFLOW/memory 旧路径改指、台账与 CHANGELOG 对齐 git 历史）**。
> **当前主线＝琛盛堂翡翠（襄阳）珠宝冷启动第 1 周（2026-10 起）**：三平台（视频号 > 小红书 > 抖音）获客引流。D1-D7 内容包已起草（草稿自标"待优化"），**尚未按平台拆分产出、未拍素材、未发布**；[REQUIREMENTS.md](docs/REQUIREMENTS.md) 验收 10 项全部未勾。

## 全局里程碑

| 里程碑 | 状态 | 说明 / 指针 |
|---|---|---|
| 五仓体系定位 + 总纲 | ✅ 完成 | [总纲.md](总纲.md) 五仓速查；本仓=运营分发层 |
| 项目结构重构（框架留 docs/，珠宝内容落 projects/jewelry/） | ✅ 完成 | 2026-10-08，见 CHANGELOG；AGENTS/总纲同步 |
| 治理档案四件套（WORKFLOW/REQUIREMENTS/DOCUMENTATION_MAP/standards/templates） | ✅ 完成 | [docs/WORKFLOW.md](docs/WORKFLOW.md)、[docs/REQUIREMENTS.md](docs/REQUIREMENTS.md) |
| 决策记录 ADR-001~006 | ✅ 完成 | [docs/project-management/decisions/](docs/project-management/decisions/)；003 珠宝人设 / 004 不出镜形式 / 005 三平台优先级 / 006 泉泉方法论吸收范围与赛道取舍均已确认 |
| 知识库归档（合并版 + 泉泉宝典 + 产品素材） | ✅ 完成 | `projects/jewelry/knowledge-base/` |
| 调研档案归档（三平台规则/案例/AI 内容调研） | ✅ 完成 | `projects/jewelry/research/`（含 `线上优先/`） |
| 旧版方案归档（24 个历史方案 + PDF/Word） | ✅ 完成 | `projects/jewelry/archive/`（不删） |
| 朋友圈 AI 工作台线归位本仓 | ✅ 完成 | 历经"迁出独立仓→挂 deps 子模块→并入本仓"三迁，2026-10-11（commit `79f03b7`）落定 `projects/wechat-moments/`，与珠宝线两线并存 |
| 治理三件套（本文件 + ISSUES + CHANGELOG） | ✅ 完成 | 2026-10-08 本次补全 |
| D1-D7 第一周内容包（脚本草稿） | 🔄 草稿完成 / ⏳ 未发布 | `projects/jewelry/platforms/D1-D7_珠宝冷启动第一周.md`（D1~D7 七天齐，自标"待优化"）；三平台产出目录 `platforms/{shipinhao,xiaohongshu,douyin}/` 仍空 |
| 拍摄 + 三平台实际发布（D1 起） | ⏳ 未开始 | REQUIREMENTS 发布/账号安全验收全未勾 |
| 每周复盘机制 | ⏳ 待首次发布后启动 | WORKFLOW §⑧（周日看数据，记录到 ISSUES） |

状态标记：✅ 完成 | 🔄 进行中 | ⏳ 待启动 | ⏸️ 暂停 | ⚠️ 有阻塞

---

## 当前焦点：珠宝冷启动第 1 周

- **人设与形式已定（ADR-003/004/005）**：襄阳翡翠店老板，接地气说真话；不出镜不 AI 配音，只拍手和货、自然光、纯音乐+硬字幕；视频号主阵地（每天 1 条）> 小红书种草（每天 1 条）> 抖音同城（隔天 1 条）。
- **D1-D7 包状态**：七天选题（立人设/立真店/立案例/立专业/立实在/立日常/立互动）三平台脚本+画面+字幕+标签已成文；但①文件自标"待优化"，②尚未按平台拆进 `platforms/` 三个空目录，③素材未拍。
- **验收差距**：[REQUIREMENTS.md](docs/REQUIREMENTS.md) 内容质量 4 项 / 发布 3 项 / 账号安全 3 项全部 `[ ]`。
- **待验证未闭环**：[memory/index.md](docs/project-management/memory/index.md) 待验证 3 项、[standards/踩坑记录.md](docs/project-management/standards/踩坑记录.md) 待验证 3 项，明细见 [ISSUES.md](ISSUES.md) I-001~I-003。

## 下一步（按优先级）

1. **用户拍板 D1-D7 脚本**（"待优化"闭环）→ 确认后按平台拆分落到 `projects/jewelry/platforms/{shipinhao,xiaohongshu,douyin}/`。
2. **拍素材**：一次拍够一周量（自然光窗边、竖拍 4K、只拍手和货，每货 3 镜头），素材入 `projects/jewelry/knowledge-base/产品素材/`。
3. **D1 起每天三平台发布**：发布前必过 [docs/sops/AI味检查SOP.md](docs/sops/AI味检查SOP.md) + [standards/合规检查清单.md](docs/project-management/standards/合规检查清单.md)；一机一号、手机流量、新号先养号 2-3 天。
4. **闭环待验证项**：AI 珠宝视频可用性 / 小红书封面配色 / 抖音是否需出镜（ISSUES I-001~I-003）。
5. **首次周复盘**：发布满一周后按 WORKFLOW §⑧ 看数据，结论回写 memory / ISSUES。

## 恢复检查清单（新会话续接逐项确认）

- [ ] 按 [AGENTS.md](AGENTS.md) §2 判断冷启动/续接；读本文件 + [memory/index.md](docs/project-management/memory/index.md) 定位结论
- [ ] 先 `git status` / `git log -1` 确认工作区干净、本地与 origin 同步再动手
- [ ] 当前到哪一步：D1-D7 脚本是否已拍板？素材拍了没？D 几已发布？——以 `projects/jewelry/platforms/` 三个平台目录实文件为准，不看本文件旧值
- [ ] 待办/阻塞项扫一遍 [ISSUES.md](ISSUES.md)
