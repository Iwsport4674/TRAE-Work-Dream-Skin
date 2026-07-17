# TRAE Work Dream Skin

A macOS theme layer for TRAE Work. Apply one of five bundled visual styles or turn your own image into a custom home screen.

The project does not modify the TRAE Work application, signature, account, projects, or chats. It loads scoped styles through a loopback debugging session and can restore the official appearance at any time.

## Quick start

1. Download and extract the repository ZIP.
2. Open the `macos` folder.
3. Double-click `Install TRAE Work Dream Skin.command`.
4. Save unsent work and approve one restart if TRAE Work is already open.

Use the desktop shortcuts to start, customize, verify, or restore the theme. See [the step-by-step guide](docs/USER-GUIDE.md) for details.

## Bundled styles

- `arcade-modern` (default)
- `pixel-8bit`
- `electric-forest`
- `sky-friends`
- `retro-2007`

All presets use the same MIT-licensed demo art. Replace it with an image you have the right to use.

## Development

```bash
cd macos
./tests/run-tests.sh
./scripts/build-release.sh
```

See [CONTRIBUTING.md](CONTRIBUTING.md), [architecture](docs/ARCHITECTURE.md), and [NOTICE.md](NOTICE.md).

## License

MIT. Adapted from [Fei-Away/Codex-Dream-Skin](https://github.com/Fei-Away/Codex-Dream-Skin).
