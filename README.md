# AyuGram GitHub Actions Build

使用 GitHub Actions 自动编译 [AyuGram](https://github.com/AyuGram/AyuGramDesktop)（Telegram Desktop fork）。

## 原理

使用 Telegram 官方的预构建 Docker 镜像 `centos_env`，在 GitHub 8 核 runner 上编译 AyuGram，产物上传为 artifact。

## 使用

### 手动触发

1. 进入 Actions → Build AyuGram → Run workflow
2. 可选参数：
   - `branch`: AyuGram 分支（默认 `dev`）
   - `jobs`: Ninja 并行度（默认 `4`）

### 自动触发

Push 到任意分支时自动构建。

## Secrets

在仓库 Settings → Secrets and variables → Actions 中设置：

| Secret | 说明 |
|--------|------|
| `TDESKTOP_API_ID` | Telegram API ID |
| `TDESKTOP_API_HASH` | Telegram API Hash |

## 产物

成功构建后，AyuGram 二进制文件会上传为 artifact（保留 7 天）。
