# KG Viz 2D Pipeline - 知识图谱 2D 可视化

## 功能特性

- **2D 力导向图**（基于 force-graph + d3-force）
- **2420 实体 + 3996 关系**（基于投行研报知识库）
- **v53 优化**: Obsidian 风格 + 默认只显示 3 类关系（对比/供应/上下游）

## 架构

- **前端**: 纯静态 HTML + JS（无后端）
- **数据**: data.json（46 MB，因 GitHub 限制使用 Git LFS 或外部存储）
- **渲染库**: force-graph 1.43.5 + d3 v7.8.5

## 本地运行

```bash
# 启动 HTTP 服务
python3 -m http.server 8093 --bind 127.0.0.1

# 浏览器打开
# http://127.0.0.1:8093/index.html
```

## 在线部署

- **仓库**: https://github.com/jinzhanxiang/kg-viz-2d-pipe
- **GitHub Pages**: https://jinzhanxiang.github.io/kg-viz-2d-pipe

## 数据说明

- `data.json`（46 MB）含完整实体、关系、逻辑链、指标、框架、关联
- GitHub 单文件限制 100 MB（用 Git LFS 解决）
- 演示数据见 `data_sample.json`（仅 50 entities）

## 版本历史

- **v53**: 默认只显示对比/供应/上下游 3 个关系
- **v52**: 移除文字背景色（v51 修复早期 showLabel 代码块失败）
- **v51**: 文字本身带类型颜色（TYPE_COLORS）
- **v50**: 字体绑节点大小 + 边类型多选 checkbox
- **v49**: 背景色优化（深蓝紫渐变 + SVG 点阵）
- **v48**: Obsidian 风格参数（log2 / 1.5x link / charge=-50）
- **v47**: LOD 节点可见性梯度（已回滚）
- **v44**: enrich indicators/frameworks/relatedEntities
- **v43 R1**: 真实逻辑链（_logicRefs）
- **v40**: Obsidian 模式（基于调研真实默认值）
- **v36**: 物理隔离 + 强聚类
- **v34**: 双击节点打开详情卡
- **v22**: 字体美化层级清晰化
