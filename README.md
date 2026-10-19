# 知发云端发布助手

在 Linux 云电脑运行知发发布服务，读取飞书中已准备好的笔记，上传至蚁小二、按排期发布到小红书并回写状态。

运行包自带 Node，支持 Linux x64、arm64。推荐 Ubuntu 22.04 或兼容的 glibc Linux，无需源码、Docker 或桌面端。

## 交给云助理安装

将[安装说明](https://github.com/xiwenran/zhifa-downloads/releases/download/linux-agent-preview-20261019/cloud-install.md)发送给具备 Linux 命令执行能力的 Grokbot 等云助理，要求按说明检测架构、校验文件、安装并检查服务。首次需要配置自己的飞书、蚁小二凭据、任务表绑定和账号白名单，确认后再启用发布。

当前版本为 **v2.3.2 (c7bc37f)**，完整构建提交 `c7bc37f8c2a5c8cebd55779e6f285f789ad07b84`。

[下载固定版本](https://github.com/xiwenran/zhifa-downloads/releases/tag/linux-agent-preview-20261019) · [校验清单](https://github.com/xiwenran/zhifa-downloads/releases/download/linux-agent-preview-20261019/SHA256SUMS)

```bash
bash install-linux.sh --base-url 'https://github.com/xiwenran/zhifa-downloads/releases/download/linux-agent-preview-20261019' --version '2.3.2' --commit 'c7bc37f8c2a5c8cebd55779e6f285f789ad07b84'
```

安装器需要 Bash、Python 3 和系统 CA 证书。默认仅安装，服务使用本机 3210 端口；发布通过 `start.sh --publish` 明确启用。同一飞书任务表只启用一台发布主机。

发布程序、账号与凭据分开分发。凭据在运行时由接收方配置，运行包不含个人密钥或账号数据。蚁小二任务提交成功与平台最终发布成功分别核验。
