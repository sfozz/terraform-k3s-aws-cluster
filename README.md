### Terraform K3S AWS Cluster

This module supports creating a k3s cluster with a postgres backend in AWS. It allows you to optionally install Rancher Server cert-manager, or import your K3S cluster into an existing Rancher Server.

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.13 |
| <a name="requirement_rancher2"></a> [rancher2](#requirement\_rancher2) | >= 1.10.3 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |
| <a name="provider_aws.r53"></a> [aws.r53](#provider\_aws.r53) | n/a |
| <a name="provider_null"></a> [null](#provider\_null) | n/a |
| <a name="provider_rancher2.bootstrap"></a> [rancher2.bootstrap](#provider\_rancher2.bootstrap) | >= 1.10.3 |
| <a name="provider_random"></a> [random](#provider\_random) | n/a |
| <a name="provider_template"></a> [template](#provider\_template) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_autoscaling_group.k3s_agent](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/autoscaling_group) | resource |
| [aws_autoscaling_group.k3s_server](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/autoscaling_group) | resource |
| [aws_db_subnet_group.private](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_subnet_group) | resource |
| [aws_launch_template.k3s_agent](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_template) | resource |
| [aws_launch_template.k3s_server](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_template) | resource |
| [aws_lb.lb](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb) | resource |
| [aws_lb.server-lb](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb) | resource |
| [aws_lb_listener.port_443](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener) | resource |
| [aws_lb_listener.port_80](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener) | resource |
| [aws_lb_listener.server-port_6443](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener) | resource |
| [aws_lb_target_group.agent-443](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_target_group) | resource |
| [aws_lb_target_group.agent-80](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_target_group) | resource |
| [aws_lb_target_group.server-6443](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_target_group) | resource |
| [aws_rds_cluster.k3s](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/rds_cluster) | resource |
| [aws_rds_cluster_instance.k3s](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/rds_cluster_instance) | resource |
| [aws_rds_cluster_parameter_group.k3s](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/rds_cluster_parameter_group) | resource |
| [aws_route53_record.rancher](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route53_record) | resource |
| [aws_security_group.database](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_security_group.ingress](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_security_group.self](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_security_group_rule.database_egress_all](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.database_self](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.ingress_egress_all](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.ingress_http](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.ingress_https](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.ingress_self](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.self_k3s_server](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_security_group_rule.self_self](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [null_resource.wait_for_rancher](https://registry.terraform.io/providers/hashicorp/null/latest/docs/resources/resource) | resource |
| [rancher2_bootstrap.admin](https://registry.terraform.io/providers/rancher/rancher2/latest/docs/resources/bootstrap) | resource |
| [random_password.k3s_cluster_secret](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/password) | resource |
| [random_pet.lb](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/pet) | resource |
| [aws_ami.ubuntu](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ami) | data source |
| [aws_route53_zone.dns_zone](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/route53_zone) | data source |
| [aws_subnet_ids.available](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/subnet_ids) | data source |
| [aws_vpc.default](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/vpc) | data source |
| [cloudinit_config.k3s_agent](https://registry.terraform.io/providers/hashicorp/template/latest/docs/data-sources/cloudinit_config) | data source |
| [cloudinit_config.k3s_server](https://registry.terraform.io/providers/hashicorp/template/latest/docs/data-sources/cloudinit_config) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_agent_image_id"></a> [agent\_image\_id](#input\_agent\_image\_id) | AMI to use for k3s agent instances | `string` | `null` | no |
| <a name="input_agent_instance_ssh_user"></a> [agent\_instance\_ssh\_user](#input\_agent\_instance\_ssh\_user) | Username for sshing into instances | `string` | `"ubuntu"` | no |
| <a name="input_agent_instance_type"></a> [agent\_instance\_type](#input\_agent\_instance\_type) | n/a | `string` | `"m5.large"` | no |
| <a name="input_agent_k3s_exec"></a> [agent\_k3s\_exec](#input\_agent\_k3s\_exec) | exec args to pass to k3s agents | `string` | `null` | no |
| <a name="input_agent_node_count"></a> [agent\_node\_count](#input\_agent\_node\_count) | Number of agent nodes to launch | `number` | `3` | no |
| <a name="input_agent_volume_type"></a> [agent\_volume\_type](#input\_agent\_volume\_type) | Volume Type for K3S Agent nodes | `string` | `"gp3"` | no |
| <a name="input_aws_azs"></a> [aws\_azs](#input\_aws\_azs) | List of AWS Availability Zones in the VPC | `list(any)` | `null` | no |
| <a name="input_aws_profile"></a> [aws\_profile](#input\_aws\_profile) | Name of the AWS Profile to use for authentication | `string` | `null` | no |
| <a name="input_aws_region"></a> [aws\_region](#input\_aws\_region) | n/a | `string` | `null` | no |
| <a name="input_certmanager_version"></a> [certmanager\_version](#input\_certmanager\_version) | Version of cert-manager to install | `string` | `"1.1.0"` | no |
| <a name="input_create_external_nlb"></a> [create\_external\_nlb](#input\_create\_external\_nlb) | Boolean that defines whether or not to create an external load balancer | `bool` | `true` | no |
| <a name="input_db_allow_major_version_upgrade"></a> [db\_allow\_major\_version\_upgrade](#input\_db\_allow\_major\_version\_upgrade) | Enable to allow major engine version upgrades when changing engine versions. | `bool` | `true` | no |
| <a name="input_db_engine_version"></a> [db\_engine\_version](#input\_db\_engine\_version) | Engine Version for RDS Database | `string` | `"10.11"` | no |
| <a name="input_db_instance_type"></a> [db\_instance\_type](#input\_db\_instance\_type) | n/a | `string` | `"db.r5.large"` | no |
| <a name="input_db_name"></a> [db\_name](#input\_db\_name) | Name of database to create in RDS | `string` | `null` | no |
| <a name="input_db_node_count"></a> [db\_node\_count](#input\_db\_node\_count) | Number of RDS database instances to launch | `number` | `1` | no |
| <a name="input_db_parameter_group_family"></a> [db\_parameter\_group\_family](#input\_db\_parameter\_group\_family) | engine family for parameter group | `string` | `"aurora-postgresql10"` | no |
| <a name="input_db_pass"></a> [db\_pass](#input\_db\_pass) | Password for RDS user | `string` | n/a | yes |
| <a name="input_db_user"></a> [db\_user](#input\_db\_user) | Username for RDS database | `string` | n/a | yes |
| <a name="input_domain"></a> [domain](#input\_domain) | n/a | `string` | `"eng.rancher.space"` | no |
| <a name="input_extra_agent_security_groups"></a> [extra\_agent\_security\_groups](#input\_extra\_agent\_security\_groups) | Additional security groups to attach to k3s agent instances | `list(any)` | `[]` | no |
| <a name="input_extra_server_security_groups"></a> [extra\_server\_security\_groups](#input\_extra\_server\_security\_groups) | Additional security groups to attach to k3s server instances | `list(any)` | `[]` | no |
| <a name="input_install_certmanager"></a> [install\_certmanager](#input\_install\_certmanager) | Boolean that defines whether or not to install Cert-Manager | `bool` | `false` | no |
| <a name="input_install_k3s_version"></a> [install\_k3s\_version](#input\_install\_k3s\_version) | Version of K3S to install | `string` | `"1.19.4+k3s1"` | no |
| <a name="input_install_rancher"></a> [install\_rancher](#input\_install\_rancher) | Boolean that defines whether or not to install Rancher | `bool` | `false` | no |
| <a name="input_k3s_cluster_secret"></a> [k3s\_cluster\_secret](#input\_k3s\_cluster\_secret) | Override to set k3s cluster registration secret | `string` | `null` | no |
| <a name="input_k3s_datastore_cafile"></a> [k3s\_datastore\_cafile](#input\_k3s\_datastore\_cafile) | Location to download RDS CA Bundle | `string` | `"/srv/rds-combined-ca-bundle.pem"` | no |
| <a name="input_k3s_datastore_endpoint"></a> [k3s\_datastore\_endpoint](#input\_k3s\_datastore\_endpoint) | Storage Backend for K3S cluster to use. Valid options are 'sqlite' or 'postgres' | `string` | `"sqlite"` | no |
| <a name="input_k3s_deploy_traefik"></a> [k3s\_deploy\_traefik](#input\_k3s\_deploy\_traefik) | Configures whether to deploy traefik ingress or not | `bool` | `true` | no |
| <a name="input_k3s_disable_agent"></a> [k3s\_disable\_agent](#input\_k3s\_disable\_agent) | Whether to run the k3s agent on the same host as the k3s server | `bool` | `false` | no |
| <a name="input_k3s_tls_san"></a> [k3s\_tls\_san](#input\_k3s\_tls\_san) | Sets k3s tls-san flag to this value instead of the default load balancer | `string` | `null` | no |
| <a name="input_letsencrypt_email"></a> [letsencrypt\_email](#input\_letsencrypt\_email) | LetsEncrypt email address to use | `string` | `"none@none.com"` | no |
| <a name="input_name"></a> [name](#input\_name) | Name for deployment | `string` | `"rancher-demo"` | no |
| <a name="input_private_subnets"></a> [private\_subnets](#input\_private\_subnets) | List of private subnet ids. | `list(any)` | `[]` | no |
| <a name="input_private_subnets_cidr_blocks"></a> [private\_subnets\_cidr\_blocks](#input\_private\_subnets\_cidr\_blocks) | List of cidr\_blocks of private subnets | `list(any)` | `[]` | no |
| <a name="input_public_subnets"></a> [public\_subnets](#input\_public\_subnets) | List of public subnet ids. | `list(any)` | `[]` | no |
| <a name="input_public_subnets_cidr_blocks"></a> [public\_subnets\_cidr\_blocks](#input\_public\_subnets\_cidr\_blocks) | List of cidr\_blocks of public subnets | `list(any)` | `[]` | no |
| <a name="input_r53_domain"></a> [r53\_domain](#input\_r53\_domain) | DNS domain for Route53 zone (defaults to domain if unset) | `string` | `""` | no |
| <a name="input_rancher2_token_key"></a> [rancher2\_token\_key](#input\_rancher2\_token\_key) | Rancher2 API token for authentication | `string` | `null` | no |
| <a name="input_rancher_chart"></a> [rancher\_chart](#input\_rancher\_chart) | Helm chart to use for Rancher install | `string` | `"rancher-stable/rancher"` | no |
| <a name="input_rancher_password"></a> [rancher\_password](#input\_rancher\_password) | Password to set for admin user during bootstrap of Rancher Server | `string` | `""` | no |
| <a name="input_rancher_version"></a> [rancher\_version](#input\_rancher\_version) | Version of Rancher to install | `string` | `"2.5.3"` | no |
| <a name="input_rds_ca_cert_identifier"></a> [rds\_ca\_cert\_identifier](#input\_rds\_ca\_cert\_identifier) | The identifier of the CA certificate for the DB instance. | `string` | `"rds-ca-2019"` | no |
| <a name="input_registration_command"></a> [registration\_command](#input\_registration\_command) | Registration command to import cluster into Rancher. Should not be used when installing Rancher in this same cluster | `string` | `""` | no |
| <a name="input_server_image_id"></a> [server\_image\_id](#input\_server\_image\_id) | AMI to use for k3s server instances | `string` | `null` | no |
| <a name="input_server_instance_ssh_user"></a> [server\_instance\_ssh\_user](#input\_server\_instance\_ssh\_user) | Username for sshing into instances | `string` | `"ubuntu"` | no |
| <a name="input_server_instance_type"></a> [server\_instance\_type](#input\_server\_instance\_type) | n/a | `string` | `"m5.large"` | no |
| <a name="input_server_k3s_exec"></a> [server\_k3s\_exec](#input\_server\_k3s\_exec) | exec args to pass to k3s server | `string` | `null` | no |
| <a name="input_server_node_count"></a> [server\_node\_count](#input\_server\_node\_count) | Number of server nodes to launch | `number` | `1` | no |
| <a name="input_server_volume_type"></a> [server\_volume\_type](#input\_server\_volume\_type) | Volume Type for K3S Server nodes | `string` | `"gp3"` | no |
| <a name="input_skip_final_snapshot"></a> [skip\_final\_snapshot](#input\_skip\_final\_snapshot) | Boolean that defines whether or not the final snapshot should be created on RDS cluster deletion | `bool` | `true` | no |
| <a name="input_ssh_keys"></a> [ssh\_keys](#input\_ssh\_keys) | SSH keys to inject into Rancher instances | `list(any)` | `[]` | no |
| <a name="input_subdomain"></a> [subdomain](#input\_subdomain) | subdomain to host rancher on, instead of using `var.name` | `string` | `null` | no |
| <a name="input_use_route53"></a> [use\_route53](#input\_use\_route53) | Configures whether to use route\_53 DNS or not | `bool` | `true` | no |
| <a name="input_vpc_id"></a> [vpc\_id](#input\_vpc\_id) | The vpc id that Rancher should use | `string` | `null` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_external_lb_dns_name"></a> [external\_lb\_dns\_name](#output\_external\_lb\_dns\_name) | n/a |
| <a name="output_k3s_cluster_secret"></a> [k3s\_cluster\_secret](#output\_k3s\_cluster\_secret) | n/a |
| <a name="output_rancher_admin_password"></a> [rancher\_admin\_password](#output\_rancher\_admin\_password) | n/a |
| <a name="output_rancher_token"></a> [rancher\_token](#output\_rancher\_token) | n/a |
| <a name="output_rancher_url"></a> [rancher\_url](#output\_rancher\_url) | n/a |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

# License

Copyright (c) 2014-2019 [Rancher Labs, Inc.](http://rancher.com)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
