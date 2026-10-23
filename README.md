# AllInOneIME language packs

English | [中文](#中文)

[AllInOneIME](https://github.com/MicroZ-LLC/AllInOneIME) comes with English only. Every other input language is a
**language pack**, downloaded only when you add that language in Settings → Input (+). This repository is where the
packs are published.

| Pack | Version | What it is | Size |
|---|---|---|---|
| `zh-pinyin` | 1.0.0 | Chinese (pinyin): the [rime-ice](https://github.com/iDvel/rime-ice) dictionaries and schema for [Rime](https://rime.im), prebuilt | 34 MB download, 126 MB installed |
| `ko-hangul` | 1.0.0 | Korean: the 2-set (Dubeolsik) layout's keys and how jamo make syllables | 1 KB |
| `hi-phonetic` | 1.0.0 | Hindi: Latin letters as they sound in Devanagari, and common words as Hindi spells them | 2 KB download, 6 KB installed |

## Coding languages

Coding mode (AllInOneIME 0.6.7 and later; hold Shift, then choose it) completes a programming language's keywords and
basic snippets as you type: `de` offers `def`. Each language is its own small pack, downloaded only when you add it in
Settings → Coding Languages, listed apart from the input languages above.

| Pack | Version | Keywords | Snippets |
|---|---|---|---|
| `python` | 1.0.0 | 99 | 24 |
| `java` | 1.0.0 | 96 | 25 |
| `go` | 1.0.0 | 68 | 24 |
| `typescript` | 1.0.0 | 104 | 24 |
| `javascript` | 1.0.1 | 65 | 7 |
| `c` | 1.0.0 | 95 | 22 |
| `cpp` | 1.0.0 | 134 | 28 |

Each is one JSON file of words and snippet text (a few KB), a release asset here (`coding-<language>-<version>`), listed
in `coding-packs.json` and signed in `coding-packs.json.sig` with the same key as `packs.json`. Like every pack they hold
data only, never code. They are AllInOneIME's own, kept in its repository (`Core/CodingPacks/`), under the app's
license (FSL-1.1-ALv2).

## How it works

- `packs.json` lists every pack version on offer: its archive's URL (a release asset of this repository), SHA-256,
  size, and the oldest app version that can use it. It is served at https://languages.allinoneime.com/packs.json.
- `packs.json.sig` is its Ed25519 signature. The app has the public key built in and reads `packs.json` only when the
  signature checks out; it then checks the archive's size and SHA-256 before unpacking it.
- A pack holds data only (schemas, dictionaries, prebuilt tables, its license). It never holds code: the engines (Rime,
  Hangul composition, Hindi transliteration) and any scripts ship inside the app. The app refuses an archive with links, executables or scripts in it.
- These keys are separate from the [plugin library](https://github.com/MicroZ-LLC/AllInOneIME-plugins)'s.

## Licenses

Each pack keeps its own license: `zh-pinyin` carries rime-ice's `LICENSE` (GPL-3.0) inside the archive. `ko-hangul` and
`hi-phonetic` are AllInOneIME's own data, kept in its repository (`LanguagePacks/`) under the same license as the app
(FSL-1.1-ALv2).

---

## 中文

AllInOneIME 本身只带英文。其他输入语言都是**语言包**，只有你在设置的「输入」里用 ＋ 加上那种语言时才下载。这个仓库用来发布语言包。

| 语言包 | 版本 | 内容 | 大小 |
|---|---|---|---|
| `zh-pinyin` | 1.0.0 | 中文（拼音）：[雾凇拼音](https://github.com/iDvel/rime-ice)的词库和方案（给 [Rime](https://rime.im) 用），预先编译好 | 下载 34 MB，装好 126 MB |
| `ko-hangul` | 1.0.0 | 韩语：两套式（두벌식）键位，以及字母怎么组成音节 | 1 KB |
| `hi-phonetic` | 1.0.0 | 印地语：拉丁字母按发音对应的天城文，以及常用词的正确拼法 | 下载 2 KB，装好 6 KB |

**编程语言包**：编码模式（AllInOneIME 0.6.7 起，长按 Shift 选择）在你打字时补全编程语言的关键字和基础代码片段，比如打 `de` 出 `def`。每种语言一个小包，只有在设置的「编程语言」里加上时才下载，和上面的输入语言分开列。目前有 `python`、`java`、`go`、`typescript`、`javascript`、`c`、`cpp`。每个包是一个几 KB 的 JSON 文件（词和片段文字），放在本仓库的 Release（`coding-<语言>-<版本>`），列在 `coding-packs.json` 里，用和 `packs.json` 同一把密钥签名（`coding-packs.json.sig`）。和所有语言包一样只有数据、没有代码；它们是 AllInOneIME 自己的，放在它的仓库里（`Core/CodingPacks/`），许可证和 App 相同（FSL-1.1-ALv2）。

- `packs.json` 列出所有语言包版本：压缩包的地址（本仓库的 Release 附件）、SHA-256、大小、能用它的最低 App 版本，地址是 https://languages.allinoneime.com/packs.json 。
- `packs.json.sig` 是它的 Ed25519 签名。App 内置公钥，签名对了才读 `packs.json`，解压前再核对压缩包的大小和 SHA-256。
- 语言包只有数据（方案、词库、预编译的表、许可证），从不包含代码：引擎（Rime、韩文组字、印地语转写）和脚本都在 App 里。压缩包里有链接、可执行文件或脚本的，App 一律拒绝。
- 签名密钥和[插件库](https://github.com/MicroZ-LLC/AllInOneIME-plugins)的是分开的。
- 每个语言包保留自己的许可证：`zh-pinyin` 的压缩包里带着雾凇拼音的 `LICENSE`（GPL-3.0）；`ko-hangul` 和 `hi-phonetic` 是 AllInOneIME 自己的数据，放在它的仓库里（`LanguagePacks/`），许可证和 App 相同（FSL-1.1-ALv2）。
