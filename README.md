# minisatip-dvbapi-descramble-watchdog

This repository hosts a single `git format-patch` for **miniSATIP** that improves DVBAPI/OSCam stability:

- **PMT-level descramble watchdog**: detects a descramble stall (scrambled TS continues, but no successful decrypt) and recovers by clearing CWs and resending CAPMT once, with a hard fallback restart.
- **Extended CW lifetime**: keeps DVBAPI CWs longer (180s) to reduce parity-switch freezes when parity is unchanged longer than the default CW timeout.

## Patch file
- `minisatip-dvbapi-descramble-watchdog.patch`

## Apply
Create a commit:

```sh
git am minisatip-dvbapi-descramble-watchdog.patch
```

Apply without creating a commit:

```sh
git apply minisatip-dvbapi-descramble-watchdog.patch
```

Upstream PR: https://github.com/catalinii/minisatip/pull/1383
