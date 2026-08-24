# 同梱している three.js

three.js **r163**（`0.163.0`）を CDN から取得してそのまま置いたもの。改変していない。
ライセンスは MIT（`LICENSE`）。

入っているのは `viewer.html` が実際に import する 4 つだけ。

| ファイル | 取得元（`https://cdn.jsdelivr.net/npm/three@0.163.0` 以下） |
|---|---|
| `three.module.js` | `build/three.module.js` |
| `addons/controls/OrbitControls.js` | `examples/jsm/controls/OrbitControls.js` |
| `addons/loaders/GLTFLoader.js` | `examples/jsm/loaders/GLTFLoader.js` |
| `addons/utils/BufferGeometryUtils.js` | `examples/jsm/utils/BufferGeometryUtils.js` |

最後のひとつは `GLTFLoader` が `../utils/BufferGeometryUtils.js` を import するため。
これを落とすと GLB の読み込みだけが失敗する。

**なぜ CDN から読まないか** — 届かないときにビューアが進捗 0% のまま無言で止まる。
読者の IP が第三者に渡ること、配布パッケージを開くのに回線が要ることも避けたい。

版を上げるときは 4 つとも同じ版で揃える。`viewer.html` の import map は
`./vendor/three/` を指しているのでパスの変更は要らない。
