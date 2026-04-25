---
title: "[[cnap-mcp|MCP Server]]"
created: 2026-04-19
updated: 2026-04-19
type: concept
tags: ['cnap', 'mcp', 'protocol']
sources: ["raw/articles/cnap-mcp-2026.md"]
---

# MCP Server

## Tools

| **Name** | **Description** | **Inputs** | **Outputs** |
| -------- | --------------- | ---------- | ----------- |
| [get_stack](#get_stack) | Returns the current CNAP stack metadata and high-level resource summary. | none | stack metadata, workspace type summary, component references |
| [get_bastion](#get_bastion) | Returns Bastion details used for secure SSH jump access into the control plane. | none | bastion metadata, access endpoint, security settings |
| [get_cli_server](#get_cli_server) | Returns CLI Server details for break-glass SRE operations. | none | cli server metadata, access path, installed tool summary |
| [list_application_versions](#list_application_versions) | Lists known software versions for an application, filtered by lifecycle state. | application_name, state (`available` or `activated`) | list of application versions matching the filter |
| [list_workspace_types](#list_workspace_types) | Lists all configured workspace type names. | none | list of `workspace_type_name` values |
| [get_workspace_type](#get_workspace_type) | Returns details for one workspace type and its associated managed resources. | workspace_type_name | compartment details and associated ingress/compute/database/application resources |
| [get_load_balancer](#get_load_balancer) | Returns details for one Application Ingress load balancer. | load_balancer_name | IP address and listener configuration details |
| [get_api_gateway](#get_api_gateway) | Returns details for one Application Ingress API Gateway. | api_gateway_name | IP/domain endpoint and deployment configuration details |
| [get_cluster](#get_cluster) | Returns details for one Application Cluster (OKE). | cluster_name | cluster metadata, networking, and workload capacity details |
| [get_database](#get_database) | Returns details for one Oracle Database resource (CDB/PDB context). | database_name | database metadata, connection profile, and service characteristics |
| [get_application_instance](#get_application_instance) | Returns details for one CNAP application instance runtime environment. | application_instance_name | application instance metadata, deployment context, and resource bindings |

## Tool Details

### `get_stack`

Returns the current CNAP stack as the top-level managed entity. Use this tool to discover the stack
identity, the input parameters, the terraform output, and the broad set of resources it governs.

**Inputs**

- None.

**Outputs**

- `stack_name` (string): Logical name of the CNAP stack.
- `stack_ocid` (string): OCI identifier of the stack.
- `compartment_name` (string): Stack compartment display name.
- `compartment_ocid` (string): OCI compartment identifier for stack scope.
- `workspace_type_count` (number): Number of configured workspace types.
- `input_parameters` (array<object>): Array of input parameters; each parameter is a { name, value } pair.
- `outputs` (array<object>): Array of output from the terraform state; each outoput is a { name, value } pair.
- `resource_summary` (object): Aggregated counts or references by managed resource type.

### `get_bastion`

Returns Bastion access details used as the secure administrative entry point to the control plane
private network.

**Inputs**

- None.

**Outputs**

- `bastion_name` (string): Bastion resource name.
- `bastion_ocid` (string): OCI identifier for the bastion resource.
- `public_endpoint` (string): Public endpoint used for bastion sessions.
- `access_mode` (string): Access mode (for example, OCI Bastion service).
- `session_policies` (array<object>): Time/session constraints and policy hints.

### `get_cli_server`

Returns details for the CNAP CLI Server used by SREs for break-glass operations and direct tooling.

**Inputs**

- None.

**Outputs**

- `cli_server_name` (string): CLI server resource name.
- `private_ip` (string): Private address used after bastion jump.

### `list_application_versions`

Lists software versions for an application and supports filtering by lifecycle state to separate
catalog availability from currently activated versions.

**Inputs**

- `application_name` (string, required): Application identifier/name.
- `state` (string, required): Version state filter. Allowed values:
  - `available`
  - `activated`

**Outputs**

- `application_name` (string): Echo of target application.
- `state` (string): Applied filter.
- `versions` (array<object>): Matching versions where each item contains:
  - `version` (string): Version label.
  - `status` (string): Lifecycle status.
  - `release_date` (string, optional): Release date/time when available.

### `list_workspace_types`

Returns all workspace type names configured in the stack. Use this as discovery input to
`get_workspace_type`.

**Inputs**

- None.

**Outputs**

- `workspace_types` (array<string>): List of workspace type names.

### `get_workspace_type`

Returns full details of one workspace type, including OCI compartment context and associated managed
resources for ingress, compute, data, and application runtime.

**Inputs**

- `workspace_type_name` (string, required): Workspace type identifier.

**Outputs**

- `workspace_type_name` (string): Workspace type identifier.
- `compartment_name` (string): OCI compartment name for this workspace type.
- `compartment_ocid` (string): OCI compartment OCID for this workspace type.
- `resources` (object): Related resources grouped by type:
  - `api_gateways` (array<object>): API Gateway resources.
  - `load_balancers` (array<object>): Load balancer resources.
  - `clusters` (array<object>): Application Cluster resources.
  - `databases` (array<object>): Oracle Database resources.
  - `application_instances` (array<object>): Application instance resources.

### `get_load_balancer`

Returns detailed information for a specific Application Ingress load balancer and its listener
configuration.

**Inputs**

- `load_balancer_name` (string, required): Target load balancer name.

**Outputs**

- `load_balancer_name` (string): Load balancer identifier.
- `ip_address` (string): Frontend IP address.
- `listeners` (array<object>): Listener details, each with:
  - `name` (string): Listener name.
  - `port` (number): Exposed port.
  - `protocol` (string): Listener protocol (for example, HTTP/HTTPS/TCP).
  - `backend_set` (string, optional): Mapped backend set name.

### `get_api_gateway`

Returns detailed information for a specific Application Ingress API Gateway and its deployments.

**Inputs**

- `api_gateway_name` (string, required): Target API Gateway name.

**Outputs**

- `api_gateway_name` (string): API Gateway identifier.
- `endpoint` (string): Public endpoint (domain/IP URL).
- `deployments` (array<object>): Deployment details, each with:
  - `name` (string): Deployment name.
  - `path_prefix` (string, optional): Path routing prefix.
  - `status` (string): Deployment status.

### `get_cluster`

Returns details for a specific Application Cluster (OKE) resource used for CNAP-managed workloads.

**Inputs**

- `cluster_name` (string, required): Target cluster name.

**Outputs**

- `cluster_name` (string): Cluster identifier.
- `cluster_ocid` (string): OCI cluster OCID.
- `kubernetes_version` (string): Kubernetes version.
- `node_pools` (array<object>): Node pool details and sizing.
- `network_profile` (object): Cluster networking summary (subnets/CNI profile).
- `lifecycle_state` (string): Cluster state.

### `get_database`

Returns details for a specific Oracle Database resource associated with CNAP application workloads.

**Inputs**

- `database_name` (string, required): Target database identifier.

**Outputs**

- `database_name` (string): Database identifier.
- `database_ocid` (string): OCI database OCID.
- `database_type` (string): Service type (for example ATP or Base DB).
- `cdb_name` (string, optional): Container Database name, if applicable.
- `pdbs` (array<string>, optional): Pluggable databases exposed for application instances.
- `connection_profile` (object, optional): Host/port/service information (non-secret fields only).
- `lifecycle_state` (string): Database lifecycle state.

Are we able to infer the vault secret name for the admin account?

### `get_application_instance`

Returns details for a specific CNAP application instance, including its deployment context and bound
platform resources.

**Inputs**

- `application_instance_name` (string, required): Target application instance name.

**Outputs**

- `application_instance_name` (string): Application instance identifier.
- `application_name` (string): Parent application/product name.
- `workspace_type_name` (string): Associated workspace type.
- `workspace_name` (string, optional): Associated workspace label/group.
- `instance_branch` (string, optional): Git branch used for instance configuration.
- `namespace` (string): Kubernetes namespace for deployment.
- `cluster_name` (string): Bound application cluster.
- `database_binding` (object, optional): Bound database/PDB reference.
- `identity_application` (string, optional): OCI Identity Domain application reference.
- `lifecycle_state` (string): Application instance lifecycle state.

Would it be useful to list the application's vault secret names based on the CNAP naming convention?
