# 主题模板

内置主题控制布局、颜色和图片裁切方式。仓库中的五套模板使用同一张 MIT 演示图，方便安全分发；真正使用时换成自己的图片即可。

## 切换主题

在终端运行：

```bash
~/.trae/trae-work-dream-skin-studio/scripts/customize-theme-macos.sh \
  --preset pixel-8bit
```

把最后一行换成下面任意预设名：

| 预设名 | 视觉特点 | 图片建议 |
| --- | --- | --- |
| `pixel-8bit` | 硬边框、像素感、复古按钮 | 像素画和复古游戏图 |
| `electric-forest` | 黄绿高对比、右侧主体 | 森林、黄色或绿色角色图 |
| `sky-friends` | 浅蓝、粉色、轻柔卡片 | 蓝天和浅色双人插画 |
| `retro-2007` | 蓝银窗口、复古软件面板 | 复古桌面与蓝色科技图 |

恢复默认 `Arcade Modern`：

```bash
~/.trae/trae-work-dream-skin-studio/scripts/customize-theme-macos.sh --reset-demo
```

## 自己改颜色

```bash
~/.trae/trae-work-dream-skin-studio/scripts/customize-theme-macos.sh \
  --image "/绝对路径/你的图片.png" \
  --name "我的 TRAE 主题" \
  --accent "#e25563" \
  --secondary "#36b8c8" \
  --highlight "#f3c96a"
```

颜色必须写成六位十六进制，例如 `#e25563`。

## 新增公开预设

复制现有预设目录，修改 `theme.json` 和图片。`visualStyle` 必须与 CSS 中的 `data-trae-dream-theme` 值一致。图片限制为 PNG、JPEG 或 WebP，处理后不超过 16 MB。

公开提交图片前，请确认自己拥有再分发权，并在 `NOTICE.md` 说明来源和许可。
