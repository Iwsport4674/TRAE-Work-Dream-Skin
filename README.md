# TRAE Work Dream Skin

给 macOS 版 TRAE Work 换主题的小工具。你可以直接使用内置风格，也可以选一张自己的图片，做成专属首页。

它不会修改 TRAE Work 应用文件、签名、账号、项目或聊天记录。主题通过本机调试会话临时加载，随时可以恢复官方外观。

> 当前仅支持 macOS。已在 Apple Silicon 与 TRAE Work 0.1.30–0.1.36 上验证；新版界面如有变化，请先运行验证工具。

## 能做什么

- 双击安装，不要求用户另外安装 Node.js
- 一键切换 5 种视觉风格
- 用自己的 PNG、JPEG、HEIC、TIFF 或 WebP 图片定制主题
- 自动检查官方应用签名与目标页面，避免注入到错误应用
- 一键截图验收，一键恢复官方界面
- 附带 Codex Skill，可自动安装、切换、验证和打包

## 30 秒安装

1. 点击 GitHub 页面右上角的 **Code → Download ZIP**。
2. 解压后打开 `macos` 文件夹。
3. 双击 `Install TRAE Work Dream Skin.command`。
4. 如果 TRAE Work 正在运行，保存未发送的内容，再按提示重启一次。

安装后，桌面会出现“启动、定制、验证、恢复”四个入口。

如果 macOS 提示文件来自未知开发者，请右键安装文件，选择“打开”，再确认一次。

## 换成自己的图片

1. 双击桌面的 `Customize TRAE Work Dream Skin.command`。
2. 选择一张横图，建议宽度 2000 像素以上。
3. 输入主题名称。
4. 等待 TRAE Work 自动刷新；如果没有刷新，按提示重启。
5. 双击 `Verify TRAE Work Dream Skin.command` 检查效果。

详细操作见 [手把手教程](docs/USER-GUIDE.md)。

## 内置主题

| 主题 | 预设名 | 适合的图片 |
| --- | --- | --- |
| Arcade Modern | 默认 | 角色立绘、游戏海报、透明背景人物 |
| Pixel 8-Bit | `pixel-8bit` | 像素画、复古游戏截图 |
| Electric Forest | `electric-forest` | 黄色、绿色、森林或高饱和图片 |
| Sky Friends | `sky-friends` | 蓝天、浅色插画、双人角色图 |
| Retro 2007 | `retro-2007` | 复古软件、蓝银色界面风格 |

命令行切换示例：

```bash
~/.trae/trae-work-dream-skin-studio/scripts/customize-theme-macos.sh \
  --preset pixel-8bit
```

更多说明见 [主题模板](docs/THEMES.md)。

## 恢复官方界面

双击桌面的 `Restore TRAE Work Dream Skin.command`。恢复操作只关闭主题和本机调试端口，不会删除任务、项目或聊天。

## 给开发者

```bash
cd macos
./tests/run-tests.sh
./scripts/build-release.sh
./scripts/build-client-release.sh "$HOME/Desktop/TRAE Work Dream Skin.zip"
```

项目结构和安全边界见 [架构说明](docs/ARCHITECTURE.md)，参与开发见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## Codex Skill

把 `skills/trae-work-dream-skin` 复制到 `~/.codex/skills/`，重启 Codex 后即可使用：

```bash
cp -R skills/trae-work-dream-skin ~/.codex/skills/
```

示例请求：`使用 $trae-work-dream-skin 把这张图片做成 TRAE Work 主题并截图验证。`

## 来源与许可

本项目基于 [Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin) 改造，使用 MIT License。演示图和第三方声明见 [NOTICE.md](NOTICE.md)。

仓库不附带 Mario、Pikachu、Hachiware、Usagi 等第三方角色素材。请只使用你拥有权利或获准使用的图片。
