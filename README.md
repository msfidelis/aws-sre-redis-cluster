# Elastic Cache (Redis) Module for SRE's 

# Features by Default

* Cluster Mode
* Encryption at rest
* Multi-AZ 
* Security Group / Access Compliance
* Transit Encryption
* Shardings
* Cloudwatch Metrics
* Custom Parameter Groups

# Variables 

| Variable                      | Default       | Required  | Type      |  Additional Info  |
--------------------------------------------------------------------------------------------|
| `name`                        | NA            | yes       | `string`  |                   |
| `node_type`                   | NA            | yes       | `string`  | See Node Types    |    
| `vpc`                         | NA            | yes       | `string`  | VPC ID            |
| `subnets `                    | NA            | yes       | `list`    | Subnet ID's       |
| `redis_version`               | `6.x`         | no        | `string`  |                   |
| `family`                      | `redis6.x`    | no        | `string`  |                   |
| `multi_az`                    | `true`        | no        | `bool`    |                   |
| `cluster_mode`                | `true`        | no        | `bool`    |                   |
| `shards`                      | `1`           | no        | `number`  |                   |
| `replicas_per_shard`          | `2`           | no        | `number`  |                   | 
| `port`                        | `6379`        | no        | `number`  |                   |
| `kms_key`                     | NA            | no        | `string`  | If you don't inform, one KMS key will be created |
| `automatic_failover_enabled`  | `true`        | no        | `bool`    |                   |
| `cidrs_to_allow`              | `[]`          | no        | `list`    | CIDR's to allow inbound and outbound traffic; if you don't inform, VPC Ranges will be enable |
| `security_groups_to_allow`    | `[]`          | no        | `list`    | Security group ID's to enable inbound and outbound traffic    | 
| `tags`                        | `{}`          | no        | `map(any)`| Tags to resources  |


# Outputs 

| Variable                      | Value                                     |
----------------------------------------------------------------------------|
| `cluster`                     | `aws_elasticache_replication_group.main`  |
| `parameter_group`             | `aws_elasticache_parameter_group.main`    | 
| `security_group`              | `security_group`                          | 

# Usage 

# Examples