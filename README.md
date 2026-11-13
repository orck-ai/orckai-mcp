# Orckai MCP Server

Give any MCP client your company's AI assistants, agents, workflows and knowledge bases from [Orckai](https://orckai.com).

Orckai is an AI agent platform for business. Its remote MCP server lets Claude, Cursor, ChatGPT and other MCP clients ask your Orckai assistants, search your knowledge bases, run your agents and start your workflows. Your organization's tool policies, approvals, guardrails, budgets and audit trail apply to every call.

## Connect

| | |
|---|---|
| URL | `https://orckai.app/api/v1/mcp` |
| Transport | Streamable HTTP (POST) |
| Auth | `Authorization: Bearer <your Orckai API key>` |
| Protocol versions | 2025-06-18, 2025-03-26, 2024-11-05 |

```json
{
  "mcpServers": {
    "orckai": {
      "url": "https://orckai.app/api/v1/mcp",
      "headers": { "Authorization": "Bearer YOUR_ORCKAI_API_KEY" }
    }
  }
}
```

Create the API key in Orckai under **API Keys**. Each tool appears only if the key has its scope.

## Tools

| Tool | Scope | What it does |
|---|---|---|
| `list_resources` | none | List the assistants, agents, workflows and knowledge bases the key can use |
| `ask_assistant` | `chat:write` | Ask an assistant a question; pass `conversation_id` to continue |
| `search_knowledge` | `kb:read` | Search a knowledge base and return the most relevant passages |
| `run_agent` | `agents:execute` | Run an agent on a goal and return its result |
| `run_workflow` | `workflows:execute` | Start a workflow; returns an execution id |
| `get_workflow_run` | `workflows:read` | Get the status and output of a workflow run |

## Links

- Docs: https://orckai.com/docs/public-api.html#mcp-endpoint
- Official MCP Registry: `app.orckai/orckai`
- Agents SDK (TypeScript): [`@orckai/agents`](https://www.npmjs.com/package/@orckai/agents)
- Free trial: https://orckai.app
