# 架构与安全边界

TRAE Work Dream Skin 是一个运行时主题层，不是修改版客户端。

## 运行流程

1. 通过 Bundle ID `com.trae.solo.app` 查找官方应用。
2. 校验应用签名与 Team ID `79M8227NKH`。
3. 使用应用自带的 Electron Node 运行注入器，不要求另装 Node.js。
4. 只在 `127.0.0.1` 打开 CDP 调试端口。
5. 只接受 URL 结尾为 `electron-browser/solo/solo-lite.html` 且含 TRAE Work 原生根节点的页面。
6. 注入带作用域的 CSS 和无交互装饰层；页面切换后自动补注入。
7. 恢复操作移除主题并关闭调试会话。

## 不做什么

- 不修改 `.app`、`app.asar`、资源文件或代码签名；
- 不读取或写入账号、会话、模型、项目和工作区配置；
- 不用截图覆盖真实界面；
- 不拦截原生按钮和输入框事件。

装饰层使用 `pointer-events: none`。测试会检查脚本语法、资源完整性、主题载入、目标页面守卫和禁止修改 `app.asar` 的规则。
