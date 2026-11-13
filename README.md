# Deployment Fixer integration

[Live offer](https://mcp.contentsweep.ai/deployment-fixer) · [workspace](https://mcp.contentsweep.ai/deployment-fixer/app) · [setup and privacy](https://mcp.contentsweep.ai/deployment-fixer/docs)

Assess bounded stateless FastAPI source/configuration and get evidence, gaps and an advisory ECS Express plan. Five trial plans per verified organization; $20/10 thereafter. A supported completed assessment consumes one plan even with blocking findings. Unsupported/incomplete/platform failures are free. Product wallets and caps are separate; no subscription or automatic replenishment.

## Free local tools

Python 3.12+ is required. Download the [wheel](https://mcp.contentsweep.ai/deployment-fixer/download), compare it to the [SHA256 manifest](https://mcp.contentsweep.ai/deployment-fixer/downloads/manifest.json), then install in a separate environment:

```sh
python3.12 -m venv .venv-deployment-fixer
.venv-deployment-fixer/bin/python -m pip install './contentsweep_deployment_fixer-1.0.0-py3-none-any.whl[mcp]'
.venv-deployment-fixer/bin/deployfixer examples/supported/source --format json
```

Example paths refer to the prepared distribution bundle. Local MCP command: `.venv-deployment-fixer/bin/deployfixer-mcp`; sole tool: `plan_deployment_readonly`. Local analysis is free and requires no organization key. In this local-only wheel, a complete assessment exits 0 even when its JSON verdict is `blocked`; incomplete analysis exits 5. Inspect the verdict and coverage. This wheel contains no hosted billing or AWS execution adapter.

## Hosted API/MCP

Verified-email signup, product activation and an organization key are required. Connect Streamable HTTP MCP to `https://mcp.contentsweep.ai/v1/deployment-fixer/mcp/` with `X-API-Key` or a bearer organization key. Never put credentials in a URL.

Use upload → preview → quote → explicit authorized start → bounded polling → report and receipt. Save and reuse the original quote/idempotency key after an uncertain response. Funding is a separate customer action. Read/download calls add no debit. See `skills/review-fastapi-deployment/references/hosted-workflow.md` for exact tools and HTTP equivalents.

Uploads accept 1–200 relative Python, Dockerfile and text configuration files, 1 MiB/file, 10 MiB source and 12 MiB encoded. Exclude private environment/credential files. Source expires in 24h, reports in 7d, operational receipts in 30d; financial identities remain separately. No imports, builds, image pulls, cloud credentials, resource changes, automatic fixes, runtime readiness verification or infrastructure cost quote.

## Examples and distribution

The checked-in `examples/` contain owned synthetic inputs and qualified reference reports. Install the maintained skill using the public-source instructions below. The engine and MCP connection are separate setup steps. `server.json` describes the hosted MCP interface; catalog acceptance and client qualification are tracked separately. Internal qualification does not establish customer adoption.

<!-- contentsweep-skill-distribution:begin -->
## Install the agent skill

Install this skill in the intended project, then choose the coding agents you use:

```sh
npx skills add founder-sweep/contentsweep-deployment-fixer --skill review-fastapi-deployment
```

For Claude Code, add the ContentSweep marketplace and install this product:

```sh
claude plugin marketplace add founder-sweep/contentsweep-supplier-feed-examples
claude plugin install contentsweep-deployment-fixer@contentsweep
```

The marketplace contains Supplier Feeds, Data Quality Gate, Inspector, Schema Mapper, DAG Doctor and Deployment Fixer. Each plugin loads its existing product skill and companion references. Installation grants no upload, spending, business-rule approval or destination-write permission. MCP connections and runtime dependencies are configured separately using the bundled [agent setup](skills/review-fastapi-deployment/references/hosted-workflow.md). Review the supported scope, privacy, free/local options and current hosted pricing before use.
<!-- contentsweep-skill-distribution:end -->

<!-- contentsweep-client-distribution:begin -->
## Gemini, Kilo, Cline and Cursor

Assess a stateless FastAPI container and prepare an advisory ECS Express plan.

Follow [client installation and recovery](CLIENTS.md). Native configuration examples, required settings, the existing skill and supported scope are included. Catalog submission and acceptance are recorded separately.
<!-- contentsweep-client-distribution:end -->

<!-- contentsweep-product-demo:begin -->
## Reproduce the product demo

Find FastAPI deployment blockers before granting AWS access.

[Public walkthrough](https://mcp.contentsweep.ai/deployment-fixer/demos/fastapi-assessment) · [Runnable package](demo/README.md) · [Native agent evidence](demo/agent-evidence.json)

Owned synthetic input, actual recorded output, expected stop cases, checksums, installation and pricing. The page reports native agent verification separately from deterministic MCP checks. Live hosted execution uses your own private credentials and explicit evaluation allowance.
<!-- contentsweep-product-demo:end -->
