# RouteWave

FPGA waveform viewer and logic analyzer — release binaries.

Website: <https://routewave.dev>
Source: <https://github.com/djmazure/logic-trace>

## Download

Pre-built binaries are published as [GitHub Releases](https://github.com/djmazure/routewave/releases).

| Platform | Asset | Notes |
|---|---|---|
| Linux x86_64 | `routewave-<ver>-linux-x86_64.tar.gz` | GUI + CLI |
| Linux x86_64 | `RouteWave-<ver>-x86_64.AppImage` | self-contained, GUI + CLI |
| macOS universal | `RouteWave-<ver>-macOS-universal.dmg` | Intel + Apple Silicon, GUI + CLI |
| Windows x86_64 | `routewave-<ver>-windows-x86_64.zip` | CLI only (cross-compiled) |

Every asset ships with a detached GPG signature (`*.asc`) and is listed in `SHA256SUMS.txt`.

## Verify your download

```bash
VERSION=1.6.0

# Import the signing key (first time only)
curl -sL https://github.com/djmazure/routewave/releases/download/v${VERSION}/PUBLIC_KEY.asc \
  | gpg --import

# Verify a signature
gpg --verify RouteWave-${VERSION}-x86_64.AppImage.asc

# Verify checksums
sha256sum -c SHA256SUMS.txt
```

## Install via the RouteRTL SDK

```bash
pip install routertl
rr routewave                          # auto-downloads on first use, opens empty viewer
rr routewave sim/waves/test.fst       # open a specific waveform
rr routewave --check dump.vcd         # validate VCD file integrity (headless)
```

To force an update of an already-installed viewer:

```bash
rr ws update-viewer
```

## Release notes

See the per-tag notes on the [releases page](https://github.com/djmazure/routewave/releases) or the upstream [`CHANGELOG.md`](https://github.com/djmazure/logic-trace/blob/main/CHANGELOG.md).

## License

RouteWave is distributed under a **Proprietary Freeware License** — free to use, redistribution restricted. See the `LICENSE` file inside each release asset for the full terms.
