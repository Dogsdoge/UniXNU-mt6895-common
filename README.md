# UniXNU MT6895 SoC common layer

Shared MediaTek MT6895 (Dimensity 8100) platform support for UniXNU device ports.

Provides: DTSI (GICv3 / UFS / clocks), kernel config fragments, XNU patch series, and kits.

## Status

Skeleton. To be filled from:
- `LittleStar-OuO/UniXNU-mt6835-common` (format reference)
- `MT6895-Mainline/linux` (hardware register/DTS truth)
- `lizi600jin/hakios-xaga/docs/BOARD.md` + `ShuiLan114514/SLNeko-XNU` (XNU 8796 driver values)

## Device facts (from live read-only probing of RMX3562)

```
SoC: MT6895 (Dimensity 8100), 4x A55 + 3x A78 + 1x A78 prime
RAM: 12 GiB @ 0x40000000
GICv3: dist 0x0C000000 (0x400) / redist 0x0C040000 (0x2000)
PSCI: SMC (psci_hvc=0)
UFS: HC 0x112B0000 / AO 0x112B8000 / PDN 0x112BC000, 4096B logical sectors
Framebuffer: 0xFE1AF000, size 0x01E50000
Panel: Tianma ILI7838A, 1080x2412
Touch: Synaptics S3910 @ I2C (to be confirmed)
MPIDR core<<8 (core_shift=8), small_cores=0x0f, cores=8
GPT: 256GB, 4096B sectors, userdata LBA 3514368..62476279
```

## Layout (planned)

```
soc.toml              - SoC identity + source pins
dts/mt6895.dtsi       - base device tree
configs/mt6895.config - kernel config fragment
patches/xnu/series    - ordered XNU patch series
kits/                 - MT6895 driver kits
```
