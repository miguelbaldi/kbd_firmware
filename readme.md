# KBD Bilateral Combinations

This fork is intended to integrate the **amazing** [sunaku](https://github.com/sunaku) work on QMK [bilateral combinations](https://sunaku.github.io/home-row-mods.html),
allowing an improved experience using [home row mods](https://precondition.github.io/home-row-mods) with Vial on Corne v4.1.

On this repository, **only v4.1 standard Vial** and **rp2040 v3** configurations has bilateral combinations customization applied.

To achieve such integration, I've forked vial-qmk and ported sunako's patch into it: [vial-qmk](https://github.com/miguelbaldi/vial-qmk)

If you need a pre compiled firmware version, please contact me, maybe I can help you.

# KBD firmware

## How to build

## 1. Setting Up Your QMK Environment

Please see https://docs.qmk.fm/#/newbs_getting_started and set up 1 to 3.

## 2. Getting source files

Please get source files of `qmk/qmk_firmware` and `vial-kb/vial-qmk`
```sh
make git-submodule
```

## 3. Building firmwares

### for VIA

```sh
make qmk-clean
kb=crkbd make qmk-init
kb=crkbd kr=rev4_1/standard km=via make qmk-compile
```
A built data will be stored on `keyboards/crkbd/qmk/qmk_firmware/.build`\
Please change `kb`, `kr` and `km` when build other.

### for Vial
```sh
make vial-qmk-clean
kb=crkbd make vial-qmk-init
kb=crkbd kr=rev4_1/standard km=vial make vial-qmk-compile
```
A built data will be stored on `keyboards/crkbd/vial-kb/vial-qmk/.build`\
Please change `kb`, `kr` and `km` when build other.

For V3 (PandaKB Gateron Low Profile)
```sh
make vial-qmk-clean
kb=crkbd_rp2040 make vial-qmk-init
kb=crkbd_rp2040 km=vial make vial-qmk-compile
```

### All cleaning and building
```sh
make update-all
```

### Troubleshooting
If you encounter any compilation errors either on qmk or vial, try the following:
```sh
cd src/vial-kb/vial-qmk
qmk git-submodule
```
