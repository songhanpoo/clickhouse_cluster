
# Ansible Role Percona XtraDB Cluster ( Mysql )

Percona XtraDB Cluster is a database clustering solution for MySQL. It ensures high availability, prevents downtime and data loss, and provides linear scalability for a growing environment.

## Role Variables
### Normal variable

| Variable | Default | Description |
|------|------|------|
| `user_default_pwd` | NA | description |
| `logger_level` | trace | description |
| `logger_log` | /var/log/clickhouse-server/clickhouse-server.log | description |
| `logger_errorlog` | /var/log/clickhouse-server/clickhouse-server.err.log | description |
| `logger_size` | 1000M | description |
| `logger_count` | 10 | description |
| `http_port` | 8123 | description |
| `tcp_port` | 9000 | description |
| `mysql_port` | 9004 | description |
| `postgresql_port` | 9005 | description |
| `listen_host` | NA | description |
| `max_connections` | 4096 | description |
| `keep_alive_timeout` | 3 | description |
| `max_concurrent_queries` | 100 | description |
| `max_server_memory_usage` | 0 | description |
| `max_thread_pool_size` | 10000 | description |
| `max_server_memory_usage_to_ram_ratio` | 0.9 | description |
| `total_memory_profiler_step` | 4194304 | description |
| `total_memory_tracker_sample_probability` | 0 | description |
| `uncompressed_cache_size` | 8589934592 | description |
| `mark_cache_size` | 5368709120 | description |
| `mmap_cache_size` | 1000 | description |
| `compiled_expression_cache_size` | 1073741824 | description |
| `path` | /var/lib/clickhouse/ | description |
| `tmp_path` | /var/lib/clickhouse/tmp/ | description |
| `user_files_path` | /var/lib/clickhouse/user_files/ | description |
| `users_xml` | users.xml | description |
| `local_directory` | /var/lib/clickhouse/access/ | description |
| `default_profile` | default | description |
| `default_database` | default | description |
| `builtin_dictionaries_reload_interval` | 3600 | description |
| `max_session_timeout` | 3600 | description |
| `default_session_timeout` | 60 | description |
| `query_log_database` | system | description |
| `query_log_table` | query_log | description |
| `query_log_partition_by` | toYYYYMM(event_date) | description |
| `query_log_flush_interval_milliseconds` | 7500 | description |
| `trace_log_database` | system | description |
| `trace_log_table` | trace_log | description |
| `trace_log_partition_by` | toYYYYMM(event_date) | description |
| `trace_log_flush_interval_milliseconds` | 7500 | description |
| `query_thread_log_database` | system | description |
| `query_thread_log_table` | query_thread_log | description |
| `query_thread_log_partition_by` | toYYYYMM(event_date) | description |
| `query_thread_log_flush_interval_milliseconds` | 7500 | description |
| `metric_log_database` | system | description |
| `metric_log_table` | metric_log | description |
| `metric_log_flush_interval_milliseconds` | 7500 | description |
| `metric_log_collect_interval_milliseconds` | 1000 | description |
| `asynchronous_metric_log_database` | system | description |
| `asynchronous_metric_log_table` | asynchronous_metric_log | description |
| `asynchronous_metric_log_flush_interval_milliseconds` | 60000 | description |
| `opentelemetry_span_log_engine` | engine MergeTree  partition by toYYYYMM(finish_date)  order by (finish_date, finish_time_us, trace_id) | description |
| `opentelemetry_span_log_database` | system | description |
| `opentelemetry_span_log_database` | opentelemetry_span_log | description |
| `opentelemetry_span_log_flush_interval_milliseconds` | 7500 | description |
| `crash_log_database` | system | description |
| `crash_log_table` | crash_log | description |
| `crash_log_flush_interval_milliseconds` | 1000 | description |
| `dictionaries_config` | *_dictionary.xml | description |
| `distributed_ddl_path` | /clickhouse/task_queue/ddl | description |

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
