# brain-slice-viewer

3D の脳モデルを任意の断面で切り、切り口に MRI と領域色を出す Web ビューア。

**[デモを開く](https://tontonkurakura.github.io/brain-slice-viewer/viewer.html)**

![断面モード](docs/screenshot-slice.png)

## 概要

- 断面モード（断面板と、それで切ったモデル）と立体モード（モデルだけ）
- アトラスは 2 つ。解剖学領域 93、血管支配領域 32
- 断面は矢状・冠状・軸位、各 256 枚 / 0.7375mm 刻み
- カーソルを乗せると領域名、クリックで選択（3 つまで）
- 標準脳は MNI152。個人の MRI ではない
- 座標はすべて world RAS (mm)。メッシュも断面も同じ数値で持つので、座標変換のコードが無い
- 依存は同梱の three.js r163 だけ。ビルド手順も外部への通信も無い
- 静的ファイルを配るだけで動く（`python3 -m http.server`）
- 仕様は [docs/spec.md](docs/spec.md)
- 用途は参照実装で、臨床で使うものではない

## ライセンス

| | |
|---|---|
| `brain_arterial.glb` / `assets/<面>/label_atlas_arterial.webp` | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)（JHU Arterial Atlas から継承） |
| `vendor/three/` | MIT |
| MNI152 / FreeSurfer / FastSurfer | 各配布元に従う |

同じ内容は、ビューアの右下「ライセンスと注意事項」からも読める。
資産を生成する Python コードは同梱していない。

## 引用

血管支配アトラスの出典。

> Liu C-F, et al. *Digital 3D Brain MRI Arterial Territories Atlas.*
> Scientific Data 10, 74 (2023). © 2021 The Johns Hopkins University

分からない点は Issues へ。
