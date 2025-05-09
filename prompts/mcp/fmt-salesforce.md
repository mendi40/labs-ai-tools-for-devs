---
mcp:
  - container:
      image: docker.repo.local.sfdc.net/sfci/a360/fmt-mcp-server/mcp/fmt-mcp-service:latest
      workdir: /app
    source:
      url: https://git.soma.salesforce.com/a360/fmt-mcp-server
---
