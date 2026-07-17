---
name: trae-work-dream-skin
description: Install, customize, switch, verify, restore, scaffold, and package TRAE Work Dream Skin themes on macOS. Use when a user asks to change the TRAE Work appearance, apply Arcade Modern, Pixel 8-Bit, Electric Forest, Sky Friends, or Retro 2007, turn an image into a TRAE Work theme, capture a verification screenshot, restore the official interface, create a reusable preset, or build an installation ZIP.
---

# TRAE Work Dream Skin

Use `scripts/trae-work-skin.sh` for routine operations.

## Safety

- Support macOS only.
- Ask the user to save unsent TRAE Work input before a possible restart.
- Never modify the official `.app`, `app.asar`, resources, or signature.
- Let the engine request restart confirmation; do not force a restart over unsaved work.
- Treat the loopback debugging port as sensitive and recommend Restore when the theme is not in use.
- Treat supplied artwork as user-owned or third-party material. Do not imply redistribution rights.

## Inspect

Run:

```bash
scripts/trae-work-skin.sh doctor
```

Use the result to confirm app identity, signature, version, active theme, and live status. If the user asks only for diagnosis, report the evidence without changing anything.

## Apply a bundled style

```bash
scripts/trae-work-skin.sh apply-preset pixel-8bit
scripts/trae-work-skin.sh apply-preset electric-forest
scripts/trae-work-skin.sh apply-preset sky-friends
scripts/trae-work-skin.sh apply-preset retro-2007
scripts/trae-work-skin.sh apply-default
```

## Customize with an image

Open the file picker:

```bash
scripts/trae-work-skin.sh customize
```

Or pass an image directly:

```bash
scripts/trae-work-skin.sh customize \
  --image "/absolute/path/to/image.png" \
  --name "我的 TRAE 主题" \
  --accent "#e25563" \
  --secondary "#36b8c8" \
  --highlight "#f3c96a"
```

Prefer a horizontal image around 2000 px wide or larger and at most 50 MB. Accepted source formats include PNG, JPEG, HEIC, TIFF, and macOS-readable WebP.

## Create a new preset

Read [references/theme-schema.md](references/theme-schema.md) completely. Scaffold an editable copy instead of changing the installed Skill:

```bash
scripts/trae-work-skin.sh scaffold "/absolute/workspace/path/TRAE-Work-Dream-Skin"
```

Add the preset and scoped CSS in that copy. Preserve unrelated changes, run tests, apply the preset, and verify it visually.

## Verify

Always verify after installation, customization, or a preset change:

```bash
scripts/trae-work-skin.sh verify "/absolute/path/trae-work-theme.png"
```

Inspect the screenshot and confirm readable contrast, visible native controls, a clickable composer, no overflow, and decorative layers with `pointer-events: none`.

## Restore

```bash
scripts/trae-work-skin.sh restore
```

Clarify that Restore does not delete tasks, projects, chats, or desktop launchers.

## Build an installation ZIP

```bash
scripts/trae-work-skin.sh build-zip "/absolute/path/TRAE Work Dream Skin.zip"
scripts/trae-work-skin.sh build-zip "/absolute/path/Pixel 8-Bit.zip" pixel-8bit
```

Inspect the archive and report its SHA-256 checksum.

## Validate

Run after changing scripts, CSS, presets, packaging, or Skill structure:

```bash
scripts/trae-work-skin.sh test
python3 /path/to/skill-creator/scripts/quick_validate.py .
```
