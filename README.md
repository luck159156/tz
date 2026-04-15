# Komari Custom Release (tz)

本仓库提供 Linux 版本主控端与 Agent 的二进制和安装脚本。

## Release 二进制

在 Releases 页面下载：

- 主控端
  - `komari-linux-amd64`
  - `komari-linux-arm64`
  - `komari-linux-386`
  - `komari-linux-riscv64`
- Agent
  - `komari-agent-linux-amd64`
  - `komari-agent-linux-arm64`
  - `komari-agent-linux-386`
  - `komari-agent-linux-arm`

## 主控端安装（install-komari.sh）

脚本地址：

- `https://raw.githubusercontent.com/luck159156/tz/main/install-komari.sh`

运行方式（root）：

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/luck159156/tz/main/install-komari.sh)
```

说明：

- 只会下载本仓库 Release 的 `komari-linux-${arch}`。
- 安装目录默认 `/opt/komari`。
- 可在脚本菜单里执行安装、升级、卸载、查看状态等。

## Agent 安装（install.sh / install-agent.sh）

脚本地址（二选一，内容一致）：

- `https://raw.githubusercontent.com/luck159156/tz/main/install.sh`
- `https://raw.githubusercontent.com/luck159156/tz/main/install-agent.sh`

运行方式（root，Linux）：

```bash
wget -qO- https://raw.githubusercontent.com/luck159156/tz/main/install.sh | sudo bash -s -- -e http://<panel-host>:25774 -t <client-token> --disable-web-ssh --disable-auto-update
```

常用参数：

- `-e` 面板地址（必填）
- `-t` 客户端 Token（必填）
- `--install-dir` 自定义安装目录
- `--install-service-name` 自定义服务名
- `--install-version <tag>` 指定版本安装
- `--install-ghproxy` 下载代理

说明：

- 仅支持 Linux。
- 脚本会从本仓库 Release 下载 `komari-agent-linux-${arch}`。

## 注意

- 请确保 Release 中已上传对应架构二进制。
- GitHub 页面里的 `Source code (zip/tar.gz)` 是平台自动生成项，不影响二进制安装。
