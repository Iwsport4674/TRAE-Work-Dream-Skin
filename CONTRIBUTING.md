# 参与贡献

欢迎提交兼容性修复、主题模板和文档改进。

## 开始前

- 仅提交你有权公开的代码和素材。
- 不要提交账号数据、日志、个人路径、应用缓存或本地截图。
- 新主题优先使用自制、公共领域或明确允许再分发的演示图，并在 `NOTICE.md` 写清来源。
- 不要修改 TRAE Work 的 `.app`、`app.asar`、资源文件或签名。

## 本地检查

```bash
cd macos
./tests/run-tests.sh
```

测试通过后，再用官方 TRAE Work 实机安装并运行验证截图。提交 Pull Request 时说明 macOS、芯片架构和 TRAE Work 版本。

## 新增主题

1. 在 `macos/presets/<主题名>/` 添加 `theme.json` 和演示图。
2. 主题名只使用小写字母、数字和连字符。
3. 需要新布局时，在 `dream-skin.css` 中用 `data-trae-dream-theme` 限定作用域。
4. 在 `macos/tests/run-tests.sh` 增加主题载入测试。
5. 更新 `docs/THEMES.md` 和素材声明。
