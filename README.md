# boltcheckout

Model Context Protocol (MCP) Server for the *boltcheckout* API.

<div align="left">
    <a href="https://www.speakeasy.com/?utm_source=boltcheckout&utm_campaign=mcp-typescript"><img src="https://www.speakeasy.com/assets/badges/built-by-speakeasy.svg" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>

<!-- Start Summary [summary] -->
## Summary

Bolt API Reference: Postman Collection:

[![](https://run.pstmn.io/button.svg)](https://god.gw.postman.com/run-collection/9136127-55d2bde1-a248-473f-95b5-64cfd02fb445?action=collection%2Ffork&collection-url=entityId%3D9136127-55d2bde1-a248-473f-95b5-64cfd02fb445%26entityType%3Dcollection%26workspaceId%3D78beee89-4238-4c5f-bd1f-7e98978744b4#?env%5BBolt%20Sandbox%20Environment%5D=W3sia2V5IjoiYXBpX2Jhc2VfdXJsIiwidmFsdWUiOiJodHRwczovL2FwaS1zYW5kYm94LmJvbHQuY29tIiwidHlwZSI6ImRlZmF1bHQiLCJlbmFibGVkIjp0cnVlfSx7ImtleSI6InRrX2Jhc2UiLCJ2YWx1ZSI6Imh0dHBzOi8vc2FuZGJveC5ib2x0dGsuY29tIiwidHlwZSI6ImRlZmF1bHQiLCJlbmFibGVkIjp0cnVlfSx7ImtleSI6ImFwaV9rZXkiLCJ2YWx1ZSI6IjxyZXBsYWNlIHdpdGggeW91ciBCb2x0IFNhbmRib3ggQVBJIGtleT4iLCJ0eXBlIjoic2VjcmV0IiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJwdWJsaXNoYWJsZV9rZXkiLCJ2YWx1ZSI6IjxyZXBsYWNlIHdpdGggeW91ciBCb2x0IFNhbmRib3ggcHVibGlzaGFibGUga2V5PiIsInR5cGUiOiJkZWZhdWx0IiwiZW5hYmxlZCI6dHJ1ZX0seyJrZXkiOiJkaXZpc2lvbl9pZCIsInZhbHVlIjoiPHJlcGxhY2Ugd2l0aCB5b3VyIEJvbHQgU2FuZGJveCBwdWJsaWMgZGl2aXNpb24gSUQ+IiwidHlwZSI6ImRlZmF1bHQiLCJlbmFibGVkIjp0cnVlfV0=)

## About
 A comprehensive Bolt API reference for interacting with Transactions, Orders, Product Catalog, Configuration, Testing, and much more.

 Note: You must also reference the [Merchant Callback API](/api-merchant) when building a managed checkout custom cart integration
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [boltcheckout](#boltcheckout)
  * [About](#about)
  * [Installation](#installation)
  * [Development](#development)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start Installation [installation] -->
## Installation

<details>
<summary>DXT (Desktop Extension)</summary>

Install the MCP server as a Desktop Extension using the pre-built [`mcp-server.dxt`](./mcp-server.dxt) file:

Simply drag and drop the [`mcp-server.dxt`](./mcp-server.dxt) file onto Claude Desktop to install the extension.

The DXT package includes the MCP server and all necessary configuration. Once installed, the server will be available without additional setup.

> [!NOTE]
> DXT (Desktop Extensions) provide a streamlined way to package and distribute MCP servers. Learn more about [Desktop Extensions](https://www.anthropic.com/engineering/desktop-extensions).

</details>

<details>
<summary>Cursor</summary>

[![Install MCP Server](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/install-mcp?name=Bolt&config=eyJtY3BTZXJ2ZXJzIjp7IkJvbHQiOnsiY29tbWFuZCI6Im5weCIsImFyZ3MiOlsiYm9sdGNoZWNrb3V0Iiwic3RhcnQiLCItLXNlcnZlci1pbmRleCIsIi4uLiIsIi0teC1hcGkta2V5IiwiLi4uIiwiLS1vLWF1dGgiLCIuLi4iXX19fQ==)

Or manually:

1. Open Cursor Settings
2. Select Tools and Integrations
3. Select New MCP Server
4. If the configuration file is empty paste the following JSON into the MCP Server Configuration:

```json
{
  "mcpServers": {
    "Bolt": {
      "command": "npx",
      "args": [
        "boltcheckout",
        "start",
        "--server-index",
        "...",
        "--x-api-key",
        "...",
        "--o-auth",
        "..."
      ]
    }
  }
}
```

</details>

<details>
<summary>Claude Code CLI</summary>

```bash
claude mcp add boltcheckout npx boltcheckout start -- --server-index ... --x-api-key ... --o-auth ...
```

</details>
<details>
<summary>Windsurf</summary>

Refer to [Official Windsurf documentation](https://docs.windsurf.com/windsurf/cascade/mcp#adding-a-new-mcp-plugin) for latest information

1. Open Windsurf Settings
2. Select Cascade on left side menu
3. Click on `Manage MCPs`. (To Manage MCPs you should be signed in with a Windsurf Account)
4. Click on `View raw config` to open up the mcp configuration file.
5. If the configuration file is empty paste the full json
```
{
  "mcpServers": {
    "Bolt": {
      "command": "npx",
      "args": [
        "boltcheckout",
        "start",
        "--server-index",
        "...",
        "--x-api-key",
        "...",
        "--o-auth",
        "..."
      ]
    }
  }
}
```
</details>
<details>
<summary>VS Code</summary>

Refer to [Official VS Code documentation](https://code.visualstudio.com/api/extension-guides/ai/mcp) for latest information

1. Open [Command Palette](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette)
1. Search and open `MCP: Open User Configuration`. This should open mcp.json file
2. If the configuration file is empty paste the full json
```
{
  "mcpServers": {
    "Bolt": {
      "command": "npx",
      "args": [
        "boltcheckout",
        "start",
        "--server-index",
        "...",
        "--x-api-key",
        "...",
        "--o-auth",
        "..."
      ]
    }
  }
}
```

</details>
<details>
<summary>Claude Desktop</summary>
Claude Desktop doesn't yet support SSE/remote MCP servers.

You need to do the following
1. Open claude Desktop
2. Open left hand side pane, then click on your Username
3. Go to `Settings`
4. Go to `Developer` tab (on the left hand side)
5. Click on `Edit Config`
Paste the following config in the configuration

```json
{
  "mcpServers": {
    "Bolt": {
      "command": "npx",
      "args": [
        "boltcheckout",
        "start",
        "--server-index",
        "...",
        "--x-api-key",
        "...",
        "--o-auth",
        "..."
      ]
    }
  }
}
```

</details>


<details>
<summary> Stdio installation via npm </summary>
To start the MCP server, run:

```bash
npx boltcheckout start --server-index ... --x-api-key ... --o-auth ...
```

For a full list of server arguments, run:

```
npx boltcheckout --help
```

</details>
<!-- End Installation [installation] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

## Development

Run locally without a published npm package:
1. Clone this repository
2. Run `npm install`
3. Run `npm run build`
4. Run `node ./bin/mcp-server.js start --server-index ... --x-api-key ... --o-auth ...`
To use this local version with Cursor, Claude or other MCP Clients, you'll need to add the following config:

```json
{
  "mcpServers": {
    "Bolt": {
      "command": "node",
      "args": [
        "./bin/mcp-server.js",
        "start",
        "--server-index",
        "...",
        "--x-api-key",
        "...",
        "--o-auth",
        "..."
      ]
    }
  }
}
```

Or to debug the MCP server locally, use the official MCP Inspector: 

```bash
npx @modelcontextprotocol/inspector node ./bin/mcp-server.js start --server-index ... --x-api-key ... --o-auth ...
```



## Contributions

While we value contributions to this MCP Server, the code is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### MCP Server Created by [Speakeasy](https://www.speakeasy.com/?utm_source=boltcheckout&utm_campaign=mcp-typescript)
