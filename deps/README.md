# deps/ · 体系子模块聚合（驱动方工作区）

> **为什么挂**：we-media-ops 是体系**驱动方**（业务意图发起方），日常要读其它仓配置、驱动调研、读总控路由/纪律、取生产产物。以 git submodule 聚合到本仓 `deps/` 下，实现在**一个项目工作区**内开发梳理，无需配置外部目录指向。
> **挂载日期**：2026-10-09（用户拍板"直接用 submodule"）
> **更新纪律**：情报/调研以**最新**为准（版本锁定不需要）——使用前执行 `git submodule update --remote --merge` 拉取各仓最新。

## 子模块清单

| 子模块 | 路径 | 角色 | 用途 |
|---|---|---|---|
| `trend-radar` | `deps/trend-radar` | ③ 情报雷达 | 读监控配置/渠道矩阵，按需驱动调研（最新情报） |
| `control-tower` | `deps/control-tower` | 总控/方法论 | 读路由表/跨仓纪律/五层现状（唯一权威源） |
| `pipeline` | `deps/pipeline` | ① 采集底座 | 取知识成品/素材（产物对接） |
| `video-studio` | `deps/video-studio` | ④ 生产执行 | 取成片/方案图（产物对接） |

## 使用方式

```bash
# 首次 clone we-media-ops 后，初始化所有子模块
git submodule update --init --recursive

# 需要读某子模块最新时，按需拉取该子模块（不盲目全量 --remote）：
#   git -C deps/<仓> fetch && git -C deps/<仓> checkout <目标commit>
# 确认无误后回到父仓只暂存该 gitlink：
#   git add deps/<仓> && git commit -m "chore: 同步 deps/<仓> 指针"
```

## 子模块按需更新 + 验证约定（2026-10-12 拍板）

- **不做全量 `git submodule update --remote`**：各仓节奏不同，全量拉易带入未审阅的代码/数据变更；改为**用到哪个、拉哪个**。
- **更新前先判定风险**：先 `git -C deps/<仓> fetch` + `git diff --stat <旧>..origin/HEAD` 看待更新提交改了什么。
  - **纯文档仓**（如 `control-tower`，改动全是 .md、无代码/配置/密钥）→ 低风险，可直接更新指针。
  - **含代码/数据仓**（如 `pipeline` 采集底座、`video-studio` 生产、`trend-radar` 监控配置）→ 滞后不擅自追，列入待办由用户拍板后再更新。
- **更新后必验证**：父仓只 `git add deps/<仓>` 该 gitlink（不连带暂存其它），`git diff --cached --submodule=log` 核对提交信息，确认无夹带再提交。
- **情报类以最新为准**的旧口径保留：仅当确实要读最新情报/路由表时，才拉对应子模块；日常引用按已锁定指针即可。

## 纪律

- **单向依赖**：只有 we-media-ops 挂子模块，其它仓不反向挂回（无循环）。
- **产物对接不变**：跨仓的"读产物"仍按各仓路径契约；子模块只是把路径收敛到 `deps/` 下。
- **控制塔定位不变**：跨仓关系/路由/纪律的唯一权威源仍在 `control-tower`，本聚合不替代。
- 若某仓不再需要，`git submodule deinit -f <path>` + 从 `.gitmodules` 移除即可，后续调整不复杂。
