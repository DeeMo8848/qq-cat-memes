# 🐾 QQ 猫猫机器人 · meme 素材聚合仓库

把 `qq-cat-bot` 用到的、原本分散在多个源仓库的 meme 模板，**通过 git 子模块统一聚合**到一
个仓库，安装时一条命令即可全部拉取。

> 本仓库不复制任何素材（源仓库共约 900MB），只保存各源仓库的**引用**（子模块指针）。
> 素材本体仍托管在各源仓库，更新时 `git submodule update --remote` 同步即可。

⚠️ 私有仓库：拉取本仓库需 GitHub 只读令牌（PAT）。（子模块指向的源仓库均为公开仓库，无需令牌。）

## 包含的子模块（源仓库）

| 子模块路径 | 源仓库 |
| --- | --- |
| `meme_emoji` | https://github.com/anyliew/meme_emoji |
| `meme-generator-contrib` | https://github.com/MemeCrafters/meme-generator-contrib |
| `crazy_emoji` | https://github.com/anyliew/crazy_emoji |
| `meme-demo` | https://github.com/USYDShawnTan/meme-demo |

## 在 qq-cat-bot 内使用

```powershell
# 一条命令拉取本仓库 + 全部 meme 子模块，并重建关键词数据
powershell -ExecutionPolicy Bypass -File .\install.ps1
```

install.ps1 会把本仓库（含子模块）克隆到 `bot/meme/custom_memes/_sources`，
随后把每个子模块的 `memes/*` 模板统一装载为可用 meme（见 meme-generator 约定）。

## 手动更新到源仓库最新

```bash
git submodule update --remote --merge
git commit -m "chore: sync meme submodules"
git push
```

## 致谢

感谢以下上游作者与仓库提供了这些 meme 模板：
[meme-generator](https://github.com/MemeCrafters/meme-generator)、`meme_emoji`、
`meme-generator-contrib`、`crazy_emoji`、`meme-demo` 等。