---
description: Load context for working with the Basecamp API
---

# /basecamp - Basecamp API Context

Loads context for working with the Basecamp API. This is a reminder that the integration exists and is configured.

## What This Command Does

Claude often forgets that Basecamp API access is available. This command:

1. Reminds Claude that Basecamp API credentials exist
2. Points to documentation for API reference
3. Reminds Claude of best practices

## Configuration

**Credentials location:** `config/secrets/basecamp.json` (gitignored) - typically in ATH_Agent repo

**API documentation:** `operations/basecamp-integration-plan.md` - typically in ATH_Agent repo

## Repo Context

This skill works from ANY directory, but the Basecamp configuration files live in specific repos:

- **If in ATH_Agent:** Check `config/secrets/basecamp.json` and `operations/basecamp-integration-plan.md`
- **If in another repo:** The credentials and docs are in `~/Agent Spaces/ATH_Agent/`

Before making API calls, verify the files exist in the current repo or navigate to ATH_Agent.

## Important Notes

- **No Basecamp MCP tool exists** - use direct API calls via curl
- Credentials are gitignored and never committed
- PUT requests replace all fields (PATCH behavior varies)

## Known Issue: Em Dash in Curl Commands

When running curl commands directly in Bash, double hyphens (`--`) can get converted to em dashes (—), causing errors like:
```
curl: option : blank argument where content is expected
```

**Workaround:** Write curl commands to a temp script file, then execute the script:

```bash
cat > /tmp/bc_request.sh << 'SCRIPT'
#!/bin/bash
ACCESS_TOKEN='your_token_here'
curl -s "https://3.basecampapi.com/..." \
  -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H "Content-Type: application/json"
SCRIPT
chmod +x /tmp/bc_request.sh && /tmp/bc_request.sh
```

This avoids character encoding issues in the shell. See KAN-76 for tracking.

## Common Operations

Refer to the integration plan for:
- Authentication flow
- Project and vault structure
- Endpoint patterns
- Account IDs and mappings

---

Ready to work with Basecamp. What do you need to do?
