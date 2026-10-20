# 数问 Studio 报表开发 Skill

WorkBuddy Skill for developing and validating DataTalk Studio reports through connected MCP tools.

## Configure the DataTalk Studio MCP

This Skill works with the DataTalk Studio MCP connector. Configure and authorize the connector in WorkBuddy before using the report-development workflow; the Skill itself does not contain credentials or establish a connection.

### Cloud Studio (recommended)

1. In WorkBuddy, add or enable the **数问·DataTalk Studio** cloud connector.
2. Complete the Studio authorization flow in the browser. Sign in or register on Studio, review the workspace and permissions, then approve the connection.
3. Return to WorkBuddy and confirm the connector is available. No API Key is required for this OAuth connection.

### Self-hosted Studio (custom MCP)

1. In WorkBuddy, open **连接器 → 自定义连接器 → 添加 MCP** and add the MCP endpoint for your Studio instance. For the current public Studio environment, use `https://studio.alenfive.top/api/mcp`; for a private deployment, use that deployment's MCP endpoint supplied by its administrator.
2. When prompted, enter a Studio API Key in WorkBuddy's credential form. Create/manage the key in Studio's **API 管理** page. Do not put the key in this repository, Skill files, report source, or chat messages.
3. Save/enable the connector and refresh it in WorkBuddy. Confirm that the Studio tools load before starting a report task.

Use one authorized Studio connection for an entire report task; do not mix cloud and self-hosted connections or move data between them implicitly. If a connector is unavailable or authorization fails, reconnect it in WorkBuddy rather than bypassing MCP with direct HTTP or database access. Local/private deployment owners should verify their endpoint and access policy with their administrator.

For credential rotation, edit the custom connector through WorkBuddy's connector settings, replace the key there, save, and refresh. Never retrieve or share the key through chat.

## Contents

- `SKILL.md` — workflow and tool-contract guidance.
- `references/analysis-session-protocol.md` — analysis-session protocol.
- `_icon.png` — DataTalk Studio icon used by WorkBuddy.

## Install

Copy this directory into WorkBuddy's local skills folder, or install it through the supported Skill management UI. Keep connector credentials in WorkBuddy's credential manager; never place API keys in this repository.
