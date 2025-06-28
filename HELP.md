# 初始化

```
# 创建虚拟环境
uv venv
# 激活虚拟环境
source .venv/bin/activate
# 安装依赖
poetry install
```

# 运行示例
```
poetry run dolphie --config-file conf/rds01.conf
```

# conf文件示例
```
# Dolphie MySQL 监控配置文件
# 您可以手动修改此文件中的任何配置

[dolphie]
refresh_interval = 1
show_additional_query_columns = true

# 可用监控面板说明：
# - dashboard: MySQL 服务器总览，包括连接数、QPS等核心指标
# - processlist: 当前会话列表，显示正在执行的查询
# - graphs: 性能指标图表，包括 QPS、TPS、连接数等趋势
# - replication: 主从复制状态监控，包括延迟时间
# - metadata_locks: 元数据锁监控，帮助诊断锁等待问题
# - ddl: DDL 操作监控，显示表结构变更
# - pfs_metrics: Performance Schema 指标监控
# - statements_summary: SQL 语句统计分析
# - proxysql_hostgroup_summary: ProxySQL 主机组状态
# - proxysql_mysql_query_rules: ProxySQL 查询规则
# - proxysql_command_stats: ProxySQL 命令统计

startup_panels = dashboard,processlist,graphs,replication,metadata_locks,statements_summary,pfs_metrics
host = 16.18.13.23
port = 3306
user = cdc_user
password = *****
```