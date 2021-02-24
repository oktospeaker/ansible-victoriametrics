# ansible-victoriametrics
Deploy docker container with victoriametricks based on official docker image victoriametrics/victoria-metrics

## Role variables
| Variable | Default value | Description |
| :---:        |     :---:      |         :---: |  
service_name                    |       victoriametrics                     |   Service name
flush_all                       |       false                               |
delete_data                     |       false                               |
user_name                       |       victoriametrics                     |   User
user_name_uid                   |       11000                               |   User ID
user_name_comment               |       victoriametrics service user        |   Comment
host_data_dir                   |       /data/victoria-metrics-data         |   Data directory on host
container_data_dir              |       /victoria-metrics-data              |   Container data directory
host_port                       |       8428                                |   Port on host
container_port                  |       8428                                |   Container port
port_type                       |       tcp                                 |   Port type
docker_image                    |       victoriametrics/victoria-metrics    |   Docker image
interval                        |       60s                                 |   Deduplication option (see https://github.com/VictoriaMetrics/VictoriaMetrics#deduplication)

### How to use
    - installation: just start the role
    - uninstallation: add --extra-vars "flush_all=true" (WARNING: It doesn't delete data directory on host!!)
    - delete data: add --extra-vars "delete_data=true"
