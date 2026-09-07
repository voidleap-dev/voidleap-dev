### Hi, I'm voidleap-dev

电子信息工程背景，专注 **AI 应用工程** 与 **嵌入式开发** 交叉方向。
独立交付可运行的 AI 工具链和拥有真实用户的线上产品。

---

## 项目作品

### 视频多模态 AI 分析工具 (video-analyzer)

`Python` `faster-whisper` `PyAV` `OpenAI Compatible API` `NiceGUI`

视频链接 → 下载 → 转写/抽帧 → 5 级 AI 分析 → Markdown 深度报告。

- 多模型有序兜底链（百炼 → DeepSeek → 智谱），未配 Key 的层自动跳过
- Token 用量统计、失败重试与降级策略
- audio / visual / full 三种分析模式
- NiceGUI 实时进度仪表盘

> 仓库私有，面试可现场演示完整流程。

---

### 本地大模型浏览器翻译扩展 (auto-translator)

`TypeScript` `React` `WXT` `Manifest V3` `Ollama`

基于本地 qwen2.5:3b 的浏览器翻译扩展，零 API 成本。

- Background Service Worker 中转请求，解决 content script 跨域限制
- 默认 3 并发队列 + 60s 超时 + 失败重试
- 选区识别 → 上下文组装 → 模型调用 → 双语注入
- 配置缓存随 storage 变化自动失效

> 仓库私有，面试可现场演示。

---

### 人脸识别考勤系统 (face-system)

`Python` `OpenCV` `ONNX Runtime GPU` `SCRFD` `ArcFace` `Tkinter`

摄像头采集 → SCRFD 人脸检测 → ArcFace 特征提取 → 余弦相似度匹配 → 考勤记录。

- RTX4060 8G 环境实测 30FPS
- 3 线程架构（采集 / 处理 / UI 分离）
- 摄像头断线恢复、热插拔检测、陌生人抓拍去重
- 活体检测 + 距离提示 + Excel 日志导出

> 仓库私有，面试可现场演示。

---

### 沈阳美食推荐平台 (小众点评)

`Astro` `TypeScript` `Supabase` `PostgreSQL` `Cloudflare Pages` `R2`

已上线运营的真实产品，覆盖 247 家餐厅，约 1500 位注册用户，日请求量 1.6K–1.8K。

- 全链路独立交付：需求 → 交互 → 数据模型 → 部署 → 运营维护
- 服务端 admin 鉴权 + Supabase RLS 行级安全
- R2 图片存储 + Cloudflare Pages 全球 CDN
- 人人可改餐厅信息（提交审核制）

> 仓库私有（历史含已轮换密钥，不公开），面试可演示线上站点与后台数据。

---

### ESP32 四足仿生机器人

`C` `Arduino` `ESP32` `PWM` `WiFi WebServer` `超声波`

12 自由度四足机器人，团队项目，负责设备控制代码调试。

- 12 路舵机 PWM 配置与零位标定（串口调试工具）
- ESP32 热点 + WebServer 网页控制（HTTP 指令触发动作）
- 超声波「检测 - 转向 - 前进」简易避障
- 排查舵机反向、角度偏差、供电压降异常

---

### 51 单片机 & STM32 开发

`C` `Keil5` `STM32CubeIDE` `I2C` `SPI` `UART` `PWM`

- 51 单片机（STC89C52RC）：LCD1602 / DS1302 / AT24C02 / 数码管 / 红外 / DS18B20 / 蜂鸣器，8 个外设驱动模块
- STM32F103C8T6：74HC595 驱动 8x8 点阵 LED，横向滚动 + 字模提取 + 亮度调节

---

## 技术栈概览

| 方向 | 技术 |
|------|------|
| AI 应用 | Python, OpenAI Compatible API, Ollama, Prompt Engineering, Multi-model Fallback |
| 视觉推理 | OpenCV, ONNX Runtime GPU, SCRFD, ArcFace, faster-whisper |
| 全栈工程 | TypeScript, React, Astro, Supabase, Cloudflare Pages, WXT (MV3) |
| 嵌入式 | C, ESP32, STM32, 51单片机, Arduino, Keil5, PWM, I2C/SPI/UART |
| 工具链 | Git, GitHub Actions, NiceGUI, Tkinter, PyInstaller |

---

## 联系方式

- Email: 3393949270@qq.com
- 求职方向: AI 应用开发 / 嵌入式软件（2027届校招）
