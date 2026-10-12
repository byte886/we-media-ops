# we-media-ops

> 自媒体运营知识库与发布素材库。不限行业，框架可复用。

## 文档边界（各文档负责什么）

| 维度 | 本文档（README.md） | 其他文档 |
|------|---------------------|----------|
| **定位** | 项目概览，给人看的目录+常用操作 | - |
| **不包含** | AI执行规则、命令、Things to Avoid | → [AGENTS.md](AGENTS.md) |
| **不包含** | 项目章程、体系格局 | → [总纲.md](总纲.md) |
| **不包含** | 详细操作流程、各环节步骤 | → [docs/WORKFLOW.md](docs/WORKFLOW.md) |
| **不包含** | 需求定义、验收标准 | → [docs/REQUIREMENTS.md](docs/REQUIREMENTS.md) |
| **不包含** | 文档索引、所有文档清单 | → [docs/DOCUMENTATION_MAP.md](docs/DOCUMENTATION_MAP.md) |
| **不包含** | 当前任务进度 | → [TASK_STATUS.md](TASK_STATUS.md) |
| **不包含** | 待解决问题 | → [ISSUES.md](ISSUES.md) |

## 仓库地址

- GitHub: https://github.com/byte886/we-media-ops （公有）

## 目录结构

> 框架/治理留 `docs/`，具体项目落 `projects/`（每项目一目录）。2026-10-12 对齐实际布局：两条内容线（珠宝线 + 朋友圈线），体系仓以子模块聚合在 `deps/`。

```
we-media-ops/
├── README.md                  # 本文件（项目概览，人读）
├── AGENTS.md                  # AI 操作手册
├── 总纲.md                    # 项目章程（可复用方法论 + 体系格局）
├── TASK_STATUS.md             # 活态进度台账（唯一进度真相）
├── ISSUES.md                  # 开放问题 / 待验证清单
├── CHANGELOG.md               # 编年变更日志（倒序）
├── .gitmodules                # 子模块清单
│
├── docs/                      # 框架与治理（跨项目复用，不随项目变）
│   ├── SYSTEM_STRATEGY.md     # 业务方向（唯一权威）
│   ├── WORKFLOW.md            # 主工作流（两条内容线 + 8 步流水线）
│   ├── REQUIREMENTS.md        # 需求与验收标准
│   ├── DOCUMENTATION_MAP.md   # 全仓文档地图
│   ├── sops/                  # 可复用操作指南
│   │   ├── AI味检查SOP.md
│   │   └── 朋友圈写作SOP.md
│   └── project-management/    # 治理档案
│       ├── decisions/         # ADR 决策记录（001~006）
│       ├── memory/            # 跨会话稳定结论（index + repo-map）
│       ├── standards/         # 规范（合规 / 不AI化 / 踩坑记录）
│       └── templates/         # 模板（每日脚本模板）
│
├── projects/                  # 内容线（每线一目录）
│   ├── jewelry/               # 内容线1：琛盛堂翡翠（襄阳）—— 当前主线
│   │   ├── knowledge-base/    # 运营知识库（泉泉宝典 + 运营方法库 + 素材）
│   │   │   ├── 运营方法库/    #   日常主用：选题池/脚本框架/合规速查/对标/复盘（七件套）
│   │   │   ├── 泉泉珠宝资料宝典/ # 泉泉原始资料（素材源，不修改）
│   │   │   └── 产品素材/      #   产品图 + 供应商样品
│   │   ├── research/          # 调研档案（三平台规则 + 案例 + AI 内容调研）
│   │   ├── platforms/         # 平台执行（D1-D7 脚本 + 三平台子目录）
│   │   │   ├── shipinhao/     #   视频号
│   │   │   ├── xiaohongshu/   #   小红书
│   │   │   └── douyin/        #   抖音
│   │   └── archive/           # 归档（旧版本，不删）
│   │
│   └── wechat-moments/        # 内容线2：朋友圈AI工作台（亦仁观点分享）
│       ├── 朋友圈_系列排期_v2/v3.md
│       ├── 朋友圈_AI工作台系列_发布手册.md
│       ├── 超级标020_行业AI工作台_OCR全文.md
│       └── 配图/              # 15 张字卡
│
├── deps/                      # 体系子模块聚合（只存指针，内容在各私有/公有仓）
│   ├── control-tower/         #   总控（五层现状总表，唯一权威）
│   ├── pipeline/              #   ① 采集底座
│   ├── trend-radar/           #   ③ 情报雷达
│   └── video-studio/          #   ④ 生产执行
│
└── scripts/                   # 浏览器自动化（小红书养号/浏览，attach 本机 Chrome）
    ├── scan_xhs.js
    └── human_browse_xhs.js
```

> **组织逻辑**：`projects/` 按**内容线**（业务主题）划分，不是按平台划分。一条内容线的多个平台 = 一条母稿改多版本（"一次拍多次用"），平台目录在内容线内部。公众号目前未启动，待启动时在同结构下新增（如 `projects/gongzhonghao/` 或并入珠宝线）。

## 当前项目：琛盛堂翡翠（襄阳）

- **平台优先级：** 视频号（私域）> 小红书（种草）> 抖音（同城）
- **人设：** 襄阳两家翡翠店老板，接地气说真话，不做仙图
- **不出镜：** 只拍手和产品，语音解说
- **合规：** 已被小红书警告过，严格遵守红线

## 常用操作

```bash
cd ~/Desktop/we-media-ops
git add <具体文件> && git commit -m "说明" && git push
cat TASK_STATUS.md   # 进度台账（根目录）
```
