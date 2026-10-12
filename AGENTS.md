# AGENTS.md — AI操作手册

> 本文档是AI代理的操作手册。执行任何任务前先读对应部分。

## 1. 项目定位

自媒体运营知识库：把珠宝运营方法论、朋友圈/小红书/抖音发布内容、AI工具方法沉淀成可复用资产。

> **鉴藏总域（heritage）**：本仓发布的内容成片/方案图来自生产仓 video-studio，工作区内经子模块 `deps/video-studio` 读取（`~/Desktop/video-studio` 为该仓的独立开发主克隆，产物口径一致）。

## 2. 执行前必读：冷启动 vs 续接

### 冷启动（首次接触本项目/跨阶段切换）
0. **本仓＝五层体系之⑤运营分发层（业务意图发起方）**：业务方向/选题/优先级以 `docs/SYSTEM_STRATEGY.md` 为唯一权威；跨仓路由/纪律的总控唯一权威在 **control-tower**（本仓不做总控，见 `总纲.md` 体系格局表）
1. `README.md` — 项目概览
2. `docs/DOCUMENTATION_MAP.md` — 全仓文档地图（先看这里定位"去哪找"）
3. `docs/project-management/memory/index.md` — 跨会话稳定结论
4. `TASK_STATUS.md`（根目录）— 当前进度
5. `ISSUES.md`（根目录）— 待解决问题

### 续接（用户说"继续/接着做"）
1. `docs/project-management/memory/index.md` — 只扫结论定位
2. `TASK_STATUS.md`（根目录）+ `ISSUES.md`（根目录）— 到哪了、下一步
3. 对应SOP：`docs/sops/朋友圈写作SOP.md` 或 `docs/sops/AI味检查SOP.md`

## 3. 目录结构（现行，2026-10-12 对齐）

> 完整树见 `README.md`；跨仓子模块见 `deps/README.md`。此处只列 AI 高频落点。

```
we-media-ops/
├── README.md                 # 项目介绍（人读）
├── AGENTS.md                 # 本文件（AI读）
├── 总纲.md                   # 项目章程（可复用方法论 + 五层体系格局）
├── TASK_STATUS.md            # 活态进度台账（根目录，唯一进度真相）
├── ISSUES.md                 # 开放问题/待验证（根目录）
├── CHANGELOG.md              # 编年变更日志（倒序，只增不改）
├── docs/                     # 框架与治理（跨项目复用）
│   ├── SYSTEM_STRATEGY.md     # 业务方向唯一权威
│   ├── WORKFLOW.md           # 主工作流（8步流水线）
│   ├── REQUIREMENTS.md       # 需求与验收标准
│   ├── DOCUMENTATION_MAP.md  # 全仓文档地图
│   ├── sops/                 # 操作指南（AI味检查 / 朋友圈写作）
│   └── project-management/
│       ├── decisions/         # ADR 决策记录（ADR-001~006，只增不改）
│       ├── memory/           # OKF 工程记忆（index + repo-map）
│       ├── standards/        # 规范（合规 / 不AI化 / 踩坑）
│       └── templates/         # 模板（每日脚本）
├── projects/                 # 内容线（每线一目录）
│   ├── jewelry/              # 珠宝冷启动主线（knowledge-base/ research/ platforms/ archive/）
│   └── wechat-moments/       # 朋友圈AI工作台线（2026-10-11 并入本仓）
├── deps/                     # 体系子模块聚合（control-tower/pipeline/trend-radar/video-studio，只存指针）
└── scripts/                  # 浏览器自动化（小红书养号/浏览，attach 本机 Chrome）
```

## 4. 核心规则

1. 新内容按内容线写入 `projects/<线>/`（珠宝线知识库落 `projects/jewelry/knowledge-base/`），再 commit；跨项目框架/规范落 `docs/`
2. 每完成一个阶段更新根目录 `TASK_STATUS.md`
3. 发现方法/坑/教训记录到根目录 `ISSUES.md`
4. 不可逆决策（人设、节奏、平台差异、赛道取舍）记录为 ADR（`docs/project-management/decisions/`，只增不改）
5. 跨会话稳定结论更新到 `docs/project-management/memory/index.md`
6. 不要把临时文件/日志提交到仓库
7. 每次发布前必须过 `docs/sops/AI味检查SOP.md` + `docs/project-management/standards/合规检查清单.md`

## 5. 常用操作

```bash
cd ~/Desktop/we-media-ops
git add <具体文件> && git commit -m "描述" && git push
cat TASK_STATUS.md   # 进度台账（根目录）
```
