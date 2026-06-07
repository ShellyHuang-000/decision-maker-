# 一纸决定

一个基于摄像头手势识别的纸团抽签小工具。用户可以在不同场景下选择纸团，通过三指捏合拖拽到中心区域打开答案，并生成适合保存/分享的抽签卡片。

## 功能

- 场景切换：答案之书、今天吃什么、买还是不买、今晚做什么等多个场景
- 答案池管理：新增/编辑/删除场景与答案，支持恢复默认内容
- 手势交互：三指捏合抓取纸团，拖到中心区域打开
- 重新抽取：答案打开后可通过双手交叉将纸团丢进废纸篓重抽
- 分享卡片：记录日期、时间、场景和答案，支持保存 PNG 与系统分享
- 鼠标预览：没有摄像头时也可以用点击/拖拽体验核心流程

## 使用方式

直接访问部署后的页面即可使用。首次开启手势模式时，浏览器会请求摄像头权限。

推荐浏览器：

- Chrome
- Edge
- Safari 最新版

本地预览可以在项目根目录启动一个静态服务器：

```bash
python3 -m http.server 8080
```

然后访问：

```text
http://localhost:8080/
```

## 手势说明

- 三指捏合：抓取纸团或确认按钮操作
- 三指捏合拖拽到中心：打开纸团
- 张开手掌并快速挥散：让纸团重新散落
- 双手交叉：将已打开的纸团揉掉并丢进废纸篓

## 隐私说明

摄像头画面仅用于浏览器本地手势识别，不会上传、保存或发送到服务器。项目没有后端服务，也不会收集用户数据。

## GitHub Pages 部署

1. 将本项目推送到 GitHub 仓库
2. 打开仓库的 `Settings`
3. 进入 `Pages`
4. Source 选择 `Deploy from a branch`
5. Branch 选择 `main`，目录选择 `/root`
6. 保存后等待 GitHub Pages 部署完成

摄像头 API 在 GitHub Pages 的 HTTPS 环境下可以正常使用。

## 第三方依赖

页面通过 CDN 加载以下依赖：

- `html2canvas`：导出分享卡片图片
- `@mediapipe/tasks-vision`：手势识别
- MediaPipe HandLandmarker 模型文件

因此首次加载手势识别功能时需要联网。

## 项目结构

```text
.
├── index.html
├── assets/
│   ├── app-icon.png
│   ├── crumpled-paper-ball.png
│   ├── unfolded-paper-clean.png
│   └── wood-table.png
├── README.md
├── LICENSE
└── .gitignore
```

## 许可证

本项目使用 MIT License。
