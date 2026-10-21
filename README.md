### Hi, I'm voidleap-dev

**AI 应用工程**方向：独立把 LLM / RAG / Agent 从零散脚本做成可运行、可服务化、可评估的完整链路。

🔍 求职意向：**AI 应用开发 / 大模型应用工程**（2027 届）。

📫 联系方式：3393949270@qq.com

> 说明：以下每个产品级项目的**可运行源码为私有仓库**（含部署配置与真实数据），公开的是**架构设计、工程决策与踩坑**文档，用于展示设计与实现能力。

---

## 项目作品

### 视频多模态 AI 分析工具 (video-analyzer)

`Python` `faster-whisper` `PyAV` `OpenAI Compatible API` `ChromaDB` `bge` `LangGraph` `FastAPI + SSE` `MCP` `NiceGUI`
→ [架构设计文档](https://github.com/voidleap-dev/video-analyzer-arch)

视频链接 → 下载 → 转写/抽帧 → 三级 AI 分析 → Markdown 报告，并把产出沉淀成 RAG 知识库 + LangGraph Agent，服务化为 FastAPI+SSE、封装成 MCP 工具。

- 多模型有序兜底链（百炼 → DeepSeek → 智谱），未配 Key 的层自动跳过
- **RAG 知识库**：bge 非对称检索 + Chroma + 向量/BM25 RRF 混合检索，检索增强问答带引用溯源
- **Agent 化**：LangGraph ReAct 循环，把 RAG/计算工具交给模型自主编排调用
- **RAG 评估**：按 RAGAS 口径自实现 recall/precision + faithfulness/relevancy（LLM-as-judge）
- **服务化**：FastAPI + SSE 流式问答 + Docker（只打包 RAG 服务层）；能力再封装为 MCP Server
- Token 用量追踪、NiceGUI 实时进度仪表盘

---

### 本地大模型浏览器翻译扩展 (auto-translator)

`TypeScript` `React` `WXT` `Manifest V3` `Ollama`
→ [架构设计文档](https://github.com/voidleap-dev/auto-translator-arch)

基于本地小模型的浏览器翻译扩展，零 API 成本，双语对照注入。

- Background Service Worker 中转请求，绕过 content script 跨域与 CSP 限制
- 单路串行队列（并发固定 1）+ 300ms 错峰 + 60s 超时 + 失败重试；配置缓存随 storage 变化自动失效
- 叶子文本块识别 → 上下文组装 → 模型调用 → 内联 span 追加注入，避免破坏 flex/grid 布局

---

### 人脸识别考勤系统 (face-system)

`Python` `OpenCV` `ONNX Runtime GPU` `SCRFD` `ArcFace` `Tkinter`
→ [架构设计文档](https://github.com/voidleap-dev/face-system-arch)

摄像头采集 → 人脸检测 → 特征提取 → 余弦相似度匹配 → 考勤记录。

- GPU 加速实时推理，三线程架构（采集 / 处理 / UI 分离）
- 摄像头断线恢复、热插拔检测、陌生人抓拍去重
- 轻量图像质量活体判定 + 距离提示；生物特征数据绝不入 Git 的隐私设计

---

### 沈阳美食推荐平台 (小众点评)

`Astro` `TypeScript` `Supabase` `PostgreSQL` `Cloudflare Pages` `R2`
→ [架构设计文档](https://github.com/voidleap-dev/xiaozhong-dianping-arch)

全链路独立交付的线上运营产品（需求 → 交互 → 数据模型 → 部署 → 运维）。

- 服务端代理 + Supabase RLS 行级安全 + CF Secret 三层密钥防护
- R2 图片存储 + Cloudflare Pages 全球 CDN；用户提交审核制
- GitHub Actions 构建门禁（类型检查 + 密钥扫描）

---

## 技术栈概览

| 方向 | 技术 |
|------|------|
| **AI 应用（主线）** | Python, OpenAI Compatible API, RAG(ChromaDB+bge+RRF), LangGraph Agent, RAGAS 口径评估, FastAPI+SSE, MCP, Ollama, Prompt Engineering, Multi-model Fallback |
| 多模态/推理 | faster-whisper, PyAV, OpenCV, ONNX Runtime GPU, SCRFD, ArcFace |
| 全栈工程 | TypeScript, React, Astro, Supabase, Cloudflare Pages/R2, WXT(MV3) |
| 工具链 | Git, GitHub Actions, Docker, NiceGUI, Tkinter, PyInstaller |
