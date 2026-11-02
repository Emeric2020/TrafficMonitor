# 本机构建与部署

- 每次修改源码或影响运行结果的配置后，都要构建受影响的目标，并部署到本机正在使用的 TrafficMonitor，再确认部署产物与构建产物一致。
- 只改宿主时构建宿主；只改独立插件时构建对应插件；两者都改时两者都构建。CodexUsage 插件由相邻的 `TrafficMonitorPlugins` 仓库独立构建。
- 当前本机运行目录为 `D:\Projects\TrafficMonitor`。部署 CodexUsage 插件时使用 `RestartTrafficMonitor.ps1`，由脚本备份旧插件、复制新 DLL、校验哈希并重启宿主。
- 部署时保留用户现有配置和偏好；除非用户明确要求，不导入预设设置或更改插件启用状态。
