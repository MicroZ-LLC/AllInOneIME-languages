# AllInOneIME language packs

English | [中文](#中文)

[AllInOneIME](https://github.com/MicroZ-LLC/AllInOneIME) comes with English only. Every other input language is a
**language pack**, downloaded only when you add that language in Settings → Input (+). This repository is where the
packs are published.

| Pack | Version | What it is | Size |
|---|---|---|---|
| `zh-pinyin` | 1.0.0 | Chinese (pinyin): the [rime-ice](https://github.com/iDvel/rime-ice) dictionaries and schema for [Rime](https://rime.im), prebuilt | 34 MB download, 126 MB installed |

## How it works

- `packs.json` lists every pack version on offer: its archive's URL (a release asset of this repository), SHA-256,
  size, and the oldest app version that can use it. It is served at https://languages.allinoneime.com/packs.json.
- `packs.json.sig` is its Ed25519 signature. The app has the public key built in and reads `packs.json` only when the
  signature checks out; it then checks the archive's size and SHA-256 before unpacking it.
- A pack holds data only (schemas, dictionaries, prebuilt tables, its license). It never holds code: the Rime engine
  and any scripts ship inside the app. The app refuses an archive with links, executables or scripts in it.
- These keys are separate from the [plugin library](https://github.com/MicroZ-LLC/AllInOneIME-plugins)'s.

## Licenses

Each pack keeps its upstream license: `zh-pinyin` carries rime-ice's `LICENSE` (GPL-3.0) inside the archive.

---

## 中文

AllInOneIME 本身只带英文。其他输入语言都是**语言包**，只有你在设置的「输入」里用 ＋ 加上那种语言时才下载。这个仓库用来发布语言包。

| 语言包 | 版本 | 内容 | 大小 |
|---|---|---|---|
| `zh-pinyin` | 1.0.0 | 中文（拼音）：[雾凇拼音](https://github.com/iDvel/rime-ice)的词库和方案（给 [Rime](https://rime.im) 用），预先编译好 | 下载 34 MB，装好 126 MB |

- `packs.json` 列出所有语言包版本：压缩包的地址（本仓库的 Release 附件）、SHA-256、大小、能用它的最低 App 版本，地址是 https://languages.allinoneime.com/packs.json 。
- `packs.json.sig` 是它的 Ed25519 签名。App 内置公钥，签名对了才读 `packs.json`，解压前再核对压缩包的大小和 SHA-256。
- 语言包只有数据（方案、词库、预编译的表、许可证），从不包含代码：Rime 引擎和脚本都在 App 里。压缩包里有链接、可执行文件或脚本的，App 一律拒绝。
- 签名密钥和[插件库](https://github.com/MicroZ-LLC/AllInOneIME-plugins)的是分开的。
- 每个语言包都保留上游的许可证：`zh-pinyin` 的压缩包里带着雾凇拼音的 `LICENSE`（GPL-3.0）。
