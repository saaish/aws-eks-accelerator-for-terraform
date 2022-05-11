# Observability Patter for Java/JMX

This module provides an automated experience around Observability for Java/JMX workloads.
It provides the following resources:

- AWS Distro For OpenTelemetry Operator and Collector
- AWS Managed Grafana Dashboard and data source
- Alerts and recording rules with AWS Managed Service for Prometheus


<!--- BEGIN_TF_DOCS --->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_grafana"></a> [grafana](#requirement\_grafana) | >= 1.13.3 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |
| <a name="provider_grafana"></a> [grafana](#provider\_grafana) | >= 1.13.3 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| <a name="module_helm_addon"></a> [helm\_addon](#module\_helm\_addon) | ../helm-addon | n/a |
| <a name="module_irsa_amp_ingest"></a> [irsa\_amp\_ingest](#module\_irsa\_amp\_ingest) | ../../../modules/irsa | n/a |
| <a name="module_irsa_amp_query"></a> [irsa\_amp\_query](#module\_irsa\_amp\_query) | ../../../modules/irsa | n/a |
| <a name="module_operator"></a> [operator](#module\_operator) | ../aws-opentelemetry-operator | n/a |

## Resources

| Name | Type |
|------|------|
| [aws_iam_policy.ingest](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_policy) | resource |
| [aws_iam_policy.query](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_policy) | resource |
| [grafana_dashboard.jmx_dashboards](https://registry.terraform.io/providers/grafana/grafana/latest/docs/resources/dashboard) | resource |
| [grafana_data_source.prometheus](https://registry.terraform.io/providers/grafana/grafana/latest/docs/resources/data_source) | resource |
| [grafana_folder.jmx_dashboards](https://registry.terraform.io/providers/grafana/grafana/latest/docs/resources/folder) | resource |
| [aws_iam_policy_document.ingest](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_iam_policy_document.query](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_addon_context"></a> [addon\_context](#input\_addon\_context) | Input configuration for the addon | <pre>object({<br>    aws_caller_identity_account_id = string<br>    aws_caller_identity_arn        = string<br>    aws_eks_cluster_endpoint       = string<br>    aws_partition_id               = string<br>    aws_region_name                = string<br>    eks_cluster_id                 = string<br>    eks_oidc_issuer_url            = string<br>    eks_oidc_provider_arn          = string<br>    irsa_iam_permissions_boundary  = string<br>    irsa_iam_role_path             = string<br>    tags                           = map(string)<br>  })</pre> | n/a | yes |
| <a name="input_amazon_prometheus_workspace_endpoint"></a> [amazon\_prometheus\_workspace\_endpoint](#input\_amazon\_prometheus\_workspace\_endpoint) | Amazon Managed Prometheus Workspace Endpoint | `string` | `null` | no |
| <a name="input_amazon_prometheus_workspace_region"></a> [amazon\_prometheus\_workspace\_region](#input\_amazon\_prometheus\_workspace\_region) | Amazon Managed Prometheus Workspace's Region | `string` | `null` | no |
| <a name="input_helm_config"></a> [helm\_config](#input\_helm\_config) | Helm Config for Prometheus | `any` | `{}` | no |
| <a name="input_manage_via_gitops"></a> [manage\_via\_gitops](#input\_manage\_via\_gitops) | Determines if the add-on should be managed via GitOps. | `bool` | `false` | no |

## Outputs

No outputs.

<!--- END_TF_DOCS --->
