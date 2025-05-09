# Salesforce FMT MCP Server

Connect to Salesforce BOM Falcon metadata APIs and manage Falcon Instances, Functional Domains, and Services.

[What is an MCP Server?](https://www.anthropic.com/news/model-context-protocol)

## Characteristics
Attribute|Details|
|-|-|
**Image Source**|Official Image
**Docker Image**|[docker.repo.local.sfdc.net/sfci/a360/fmt-mcp-server/mcp/fmt-mcp-service](https://docker.repo.local.sfdc.net/sfci/a360/fmt-mcp-server/mcp/fmt-mcp-service)
**Author**|Salesforce
**Repository**|https://git.soma.salesforce.com/a360/fmt-mcp-server
**Dockerfile**|https://git.soma.salesforce.com/a360/fmt-mcp-server/blob/main/Dockerfile
**Docker Image built by**|Salesforce CI
**Licence**|Proprietary software of Salesforce.com, Inc.

## Available Tools
Tools provided by this Server|Short Description
-|-
`list_falcon_instances`|List all existing Falcon Instances in the metadata environment|
`list_functional_domains`|List all Functional Domains (FDs) within a specific Falcon Instance (FI)|
`list_services`|List services with optional filters for service name and team name|
`get_service_definition`|Get detailed service definition information for a specific service|
`list_service_instances`|List all instances of a specific service across Falcon Instances and Functional Domains|
`list_fd_cidr_blocks`|List all CIDR blocks for a specific Functional Domain|
`mcp_documentation`|Get documentation for Salesforce BOM Falcon metadata tools and rules|
`list_service_teams`|List service teams across Falcon Instances and Functional Domains|
`service_team_definition`|Get detailed definition information for a specific service team|
`get_fi_definition`|Get detailed definition information for a specific Falcon Instance|
`get_fd_definition`|Get detailed definition information for a specific Functional Domain within a Falcon Instance|

---
## Tools Details

#### Tool: **`list_falcon_instances`**
List all existing Falcon Instances in the metadata environment.

---
#### Tool: **`list_functional_domains`**
List all Functional Domains (FDs) within a specific Falcon Instance (FI).
Parameters|Type|Description
-|-|-
`falcon_instance`|`string`|The name of the Falcon Instance to list Functional Domains from.

---
#### Tool: **`list_services`**
List services with optional filters for service name and team name.
Parameters|Type|Description
-|-|-
`service_name`|`string` *optional*|Filter for service name (partial match)
`team_name`|`string` *optional*|Filter for team name (partial match)

---
#### Tool: **`get_service_definition`**
Get detailed service definition information for a specific service.
Parameters|Type|Description
-|-|-
`service_name`|`string`|The name of the service to get definition for

---
#### Tool: **`list_service_instances`**
List all instances of a specific service across Falcon Instances and Functional Domains.
Parameters|Type|Description
-|-|-
`service_name`|`string` *optional*|Filter for service name (partial match)
`falcon_instance`|`string` *optional*|Filter for Falcon Instance name (partial match)
`falcon_domain`|`string` *optional*|Filter for Functional Domain name (partial match)
`service_team`|`string` *optional*|Filter for service team name (partial match)

---
#### Tool: **`list_fd_cidr_blocks`**
List all CIDR blocks for a specific Functional Domain.
Parameters|Type|Description
-|-|-
`falcon_instance`|`string`|The name of the Falcon Instance
`falcon_domain`|`string`|The name of the Functional Domain

---
#### Tool: **`mcp_documentation`**
Get documentation for Salesforce BOM Falcon metadata tools and rules.

---
#### Tool: **`list_service_teams`**
List service teams across Falcon Instances and Functional Domains.
Parameters|Type|Description
-|-|-
`falcon_instance`|`string` *optional*|The name of the Falcon Instance (required for use case 1, optional for use case 2)
`falcon_domain`|`string` *optional*|The name of the Functional Domain (required for use case 1, optional for use case 2)
`service_team`|`string` *optional*|The name of the service team (required for use case 2, optional for use case 1)

---
#### Tool: **`service_team_definition`**
Get detailed definition information for a specific service team.
Parameters|Type|Description
-|-|-
`service_team`|`string`|The name of the service team to get definition for

---
#### Tool: **`get_fi_definition`**
Get detailed definition information for a specific Falcon Instance.
Parameters|Type|Description
-|-|-
`falcon_instance`|`string`|The name of the Falcon Instance to get definition for

---
#### Tool: **`get_fd_definition`**
Get detailed definition information for a specific Functional Domain within a Falcon Instance.
Parameters|Type|Description
-|-|-
`falcon_instance`|`string`|The name of the Falcon Instance containing the Functional Domain
`falcon_domain`|`string`|The name of the Functional Domain to get definition for

---
## Use this MCP Server

```json
{
  "mcpServers": {
    "salesforce-bom-metadata-api": {
      "command": "docker",
      "args": [
        "run",
        "-i",
        "--rm",
        "--pull",
        "always",
        "docker.repo.local.sfdc.net/sfci/a360/fmt-mcp-server/mcp/fmt-mcp-service:latest"
      ]
    }
  }
}
```

[Why is it safer to run MCP Servers with Docker?](https://www.docker.com/blog/the-model-context-protocol-simplifying-building-ai-apps-with-anthropic-claude-desktop-and-docker/) 