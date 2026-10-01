# YourGPT for Codex / OpenAI

Analyze customer conversations, spot recurring issues, fix knowledge gaps, and tune YourGPT agents for better answers.

## Install

Add `YourGPT/yourgpt-openai-plugin` as a repository marketplace in a compatible host, then install YourGPT. This repository contains the plugin at its root.

## Connect

The bundled MCP configuration points to https://mcp.yourgpt.ai/v1/platform/mcp. Install the plugin and choose Connect or Authenticate in your host. YourGPT opens a browser page where you enter a platform API token and approve access. An organization owner can create the token under Organization Settings → API Tokens. Project mcp- tokens are not accepted. Never paste credentials into chat or tracked files. No customer environment variable is required.

The app receives separate OAuth credentials; the API token stays encrypted on the YourGPT service. The connection supports all 66 platform operations, including writes and organization administration, within the supplied key's permissions. The review skills are read-only; fix-knowledge-gap and agent-tuning write only after confirmation. Skills do not restrict the connection itself. To remove access, disconnect in a host that revokes its OAuth grant or revoke the dedicated platform token in YourGPT.

## Workflows

- support-review: summarize support metrics and selected conversation examples.
- knowledge-audit: investigate training status and knowledge gaps.
- fix-knowledge-gap: correct a wrong or missing answer and confirm the bot answers correctly.
- agent-tuning: test a persona and model in the playground and apply the best one after approval.

## Status

The hosted connection uses OAuth authorization code with S256 PKCE. Availability in this repository is independent of official directory approval. Validate the connection in your intended host. Version 0.1.3 exposes only search_tools and execute_tool on the existing endpoint. Search returns matching operation schemas on demand; execute dispatches to the same 66 existing handlers.

## Data access

The host connects to mcp.yourgpt.ai. The MCP service calls api.yourgpt.ai using the authorized platform token. It retrieves the project and customer data needed for your request. There are no local scripts, hooks, telemetry, or duplicate API implementations in this package.

## Publisher links

[Website](https://yourgpt.ai) · [Support](https://help.yourgpt.ai/) · [Privacy](https://yourgpt.ai/privacy) · [Terms](https://yourgpt.ai/terms)

## Development

Generated release package. Report issues at https://github.com/YourGPT/yourgpt-openai-plugin/issues. Licensed under MIT; see LICENSE.
