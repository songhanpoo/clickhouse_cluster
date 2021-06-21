
# Ansible Role Clickhouse

Percona XtraDB Cluster is a database clustering solution for MySQL. It ensures high availability, prevents downtime and data loss, and provides linear scalability for a growing environment.

## Role Variables
### Normal variable

| Variable | Default | Description |
|------|------|------|
| `user_default_pwd` | NA | set password for user default before install clickhouse |
| `logger_level` | trace | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `logger_log` | /var/log/clickhouse-server/clickhouse-server.log | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `logger_errorlog` | /var/log/clickhouse-server/clickhouse-server.err.log | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `logger_size` | 1000M | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `logger_count` | 10 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `http_port` | 8123 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `tcp_port` | 9000 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `mysql_port` | 9004 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `postgresql_port` | 9005 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `listen_host` | NA | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `max_connections` | 4096 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `keep_alive_timeout` | 3 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `max_concurrent_queries` | 100 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `max_server_memory_usage` | 0 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `max_thread_pool_size` | 10000 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `max_server_memory_usage_to_ram_ratio` | 0.9 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `total_memory_profiler_step` | 4194304 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `total_memory_tracker_sample_probability` | 0 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `uncompressed_cache_size` | 8589934592 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `mark_cache_size` | 5368709120 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `mmap_cache_size` | 1000 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `compiled_expression_cache_size` | 1073741824 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `path` | /var/lib/clickhouse/ | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `tmp_path` | /var/lib/clickhouse/tmp/ | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `user_files_path` | /var/lib/clickhouse/user_files/ | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `users_xml` | users.xml | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `local_directory` | /var/lib/clickhouse/access/ | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `default_profile` | default | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `default_database` | default | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `builtin_dictionaries_reload_interval` | 3600 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `max_session_timeout` | 3600 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `default_session_timeout` | 60 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `query_log_database` | system | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `query_log_table` | query_log | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `query_log_partition_by` | toYYYYMM(event_date) | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `query_log_flush_interval_milliseconds` | 7500 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `trace_log_database` | system | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `trace_log_table` | trace_log | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `trace_log_partition_by` | toYYYYMM(event_date) | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `trace_log_flush_interval_milliseconds` | 7500 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `query_thread_log_database` | system | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `query_thread_log_table` | query_thread_log | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `query_thread_log_partition_by` | toYYYYMM(event_date) | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `query_thread_log_flush_interval_milliseconds` | 7500 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `metric_log_database` | system | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `metric_log_table` | metric_log | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `metric_log_flush_interval_milliseconds` | 7500 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `metric_log_collect_interval_milliseconds` | 1000 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `asynchronous_metric_log_database` | system | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `asynchronous_metric_log_table` | asynchronous_metric_log | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `asynchronous_metric_log_flush_interval_milliseconds` | 60000 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `opentelemetry_span_log_engine` | engine MergeTree  partition by toYYYYMM(finish_date)  order by (finish_date, finish_time_us, trace_id) | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `opentelemetry_span_log_database` | system | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `opentelemetry_span_log_database` | opentelemetry_span_log | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `opentelemetry_span_log_flush_interval_milliseconds` | 7500 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `crash_log_database` | system | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `crash_log_table` | crash_log | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `crash_log_flush_interval_milliseconds` | 1000 | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `dictionaries_config` | *_dictionary.xml | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |
| `distributed_ddl_path` | /clickhouse/task_queue/ddl | [Reference](https://github.com/ClickHouse/ClickHouse/blob/master/programs/server/config.xml) |

### Cluster variable
| Variable | Default | Description |
|------|------|------|
| `remote_servers` | NA | Array|
| `clusterName` | NA | string |
| `cluster` | NA | Array |
| `shard` | NA | An array include multi replica,host,port |
| `replica` | NA | string |
| `host` | NA | string |
| `port` | NA | string |

## Run Locally

Clone the project

```bash
  git clone https://github.com/songhanpoo/clickhouse_cluster.git
```

Go to the project directory

```bash
  cd clickhouse_cluster
```

Edit tests/inventories.yaml

```yaml
  all:
  hosts:
    node1:
      ansible_ssh_host: 172.xx.xx.xx
      ip: 172.xx.xx.xx
      ansible_ssh_user: vagrant
      ansible_ssh_private_key_file: ~/.ssh/id_rsa
      # ansible_ssh_common_args: -o "StrictHostKeyChecking no" -o ProxyCommand="ssh -W %h:%p -q root@172.xx.xx.xx"
    node2:
      ansible_ssh_host: 172.xx.xx.xx
      ip: 172.xx.xx.xx
      ansible_ssh_user: vagrant
      ansible_ssh_private_key_file: ~/.ssh/id_rsa
      # ansible_ssh_common_args: -o "StrictHostKeyChecking no" -o ProxyCommand="ssh -W %h:%p -q root@172.xx.xx.xx"
  children:
    master:
      hosts:
        node1:
    backup:
      hosts:
        node2:
```


Edit tests/test.yaml ( playbook )
Below default config standalone

```yaml
---
- hosts: all
  become: true
  become_method: sudo
  gather_facts: true
  roles:
  - {role: 'clickhouse',tags: 'clickhouse'}
  vars:
#-------Clickhouse--------#
    # user_default_pwd: wh0lov3me
    # logger_level: trace
    # logger_log: /var/log/clickhouse-server/clickhouse-server.log
    # logger_errorlog: /var/log/clickhouse-server/clickhouse-server.err.log
    # logger_size: 1000M
    # logger_count: 10
    # http_port: 8123
    # tcp_port: 9000
    # mysql_port: 9004
    # postgresql_port: 9005
    # interserver_http_port: 9009
    # listen_host: 0.0.0.0
    # max_connections: 4096
    # keep_alive_timeout: 3
    # max_concurrent_queries: 100
    # max_server_memory_usage: 0
    # max_thread_pool_size: 10000
    # max_server_memory_usage_to_ram_ratio: "0.9"
    # total_memory_profiler_step: 4194304
    # total_memory_tracker_sample_probability: 0
    # uncompressed_cache_size: 8589934592
    # mark_cache_size: 5368709120
    # mmap_cache_size: 1000
    # compiled_expression_cache_size: 1073741824
    # path: /var/lib/clickhouse/
    # tmp_path: /var/lib/clickhouse/tmp/
    # user_files_path: /var/lib/clickhouse/user_files/
    # users_xml: users.xml
    # local_directory: /var/lib/clickhouse/access/
    # default_profile: default
    # default_database: default
    --without fault tolerance--#
    remote_servers: [] 
    # builtin_dictionaries_reload_interval: 3600
    # max_session_timeout: 3600
    # default_session_timeout: 60
    # query_log_database: system
    # query_log_table: query_log
    # query_log_partition_by: 'toYYYYMM(event_date)'
    # query_log_flush_interval_milliseconds: 7500
    # trace_log_database: system
    # trace_log_table: trace_log
    # trace_log_partition_by: 'toYYYYMM(event_date)'
    # trace_log_flush_interval_milliseconds: 7500
    # query_thread_log_database: system
    # query_thread_log_table: query_thread_log
    # query_thread_log_partition_by: 'toYYYYMM(event_date)'
    # query_thread_log_flush_interval_milliseconds: 7500
    # metric_log_database: system
    # metric_log_table: metric_log
    # metric_log_flush_interval_milliseconds: 7500
    # metric_log_collect_interval_milliseconds: 1000
    # asynchronous_metric_log_database: system
    # asynchronous_metric_log_table: asynchronous_metric_log
    # asynchronous_metric_log_flush_interval_milliseconds: 60000
    # opentelemetry_span_log_engine: | 
    #   engine MergeTree
    #   partition by toYYYYMM(finish_date)
    #   order by (finish_date, finish_time_us, trace_id)
    # opentelemetry_span_log_database: "system"
    # opentelemetry_span_log_database: "opentelemetry_span_log"
    # opentelemetry_span_log_flush_interval_milliseconds: 7500
    # crash_log_database: "system"
    # crash_log_table: "crash_log"
    # crash_log_flush_interval_milliseconds: 1000
    # dictionaries_config: "*_dictionary.xml"
    # distributed_ddl_path: "/clickhouse/task_queue/ddl"
```

Below config for clustering
- 1 shard with 2 replica 👌

```yaml
---
- hosts: all
  become: true
  become_method: sudo
  gather_facts: true
  roles:
  - {role: 'clickhouse',tags: 'clickhouse'}
  vars:
#-------Clickhouse--------#
    #--with 1 cluster, every shard have two replica--#
    remote_servers:
    - clusterName: example_cluster
      cluster:
      - shard:
        - replica:
          host: "node2"
          port: "9000"
          priority: 1
        - replica:
          host: "node3"
          port: "9000"
          priority: 1
```
Run below command for testing connection
```bash
ansible -i tests/inventory.yml -m ping
```

Run below command for deploy
```bash
ansible-playbook -i tests/inventory.yml tests/test.yml 
```



## Support

For support, email songhanpoo@gmail.com.

## Authors

- [@songhanpoo](https://www.github.com/songhanpoo)
