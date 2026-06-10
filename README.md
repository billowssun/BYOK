# BYOK

一个本地运行的多模型创作工作台。你可以在浏览器里配置自己的 API Key，调用不同供应商完成图片生成、视频任务、音频转文字和文字转语音。

## 功能

- 图片生成与参考图编辑
- 视频生成任务创建与状态查询
- 音频转文字
- 文字转语音
- 多供应商 Key 管理
- 本地历史记录
- 浅色 / 深色模式自适应

## 支持的供应商

- OpenAI
- Gemini
- 阿里云百炼
- MiniMax
- 火山引擎
- 可灵 Kling
- 讯飞开放平台

## 本地启动

```bash
npm start
```

默认地址：

```text
http://localhost:4173
```

如果需要换端口：

```bash
PORT=3000 npm start
```

Windows PowerShell：

```powershell
$env:PORT=3000; npm start
```

## BYOK 说明

BYOK 是 Bring Your Own Key。这个项目不会在服务端保存你的密钥，前端会把当前请求所需的 Key 发送给本地 Node 服务，由本地服务转发到你选择的模型接口。

如果勾选“保存在当前浏览器”，密钥会保存在浏览器本地存储中，并使用 Web Crypto 做本地加密。它适合个人可信设备上的便利使用，不应被当作强安全边界。

## 项目结构

```text
.
├─ server.js
├─ package.json
└─ public
   ├─ index.html
   ├─ styles.css
   └─ app.js
```

## 后续现代化方向

- 拆分 `server.js` 中的 provider adapter
- 拆分前端状态、API、视图模块
- 增加基础测试和格式化工具
- 收紧生产环境 CORS 与 Base URL 校验
