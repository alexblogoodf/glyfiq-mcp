# 🩺 Glyfiq MCP Server

> **Hand-drawn medical and health icons for AI agents.**  
> Search by medical terminology and get exact SVG code.  
> 🚫 *No AI-generated paths. No invented icon names. 100% authentic.*

[![Version](https://img.shields.io/badge/version-1.4.0-blue.svg)](https://glyfiq.link)
[![License](https://img.shields.io/badge/license-Proprietary-gray.svg)](https://github.com/alexblogoodf/glyfiq-mcp/blob/main/LICENSE.md)
[![MCP Registry](https://img.shields.io/badge/MCP-Official%20Registry-orange.svg)](https://registry.modelcontextprotocol.io/?q=glyfiq)
[![Glyfiq Medical & Health Icons MCP connector – tool definition quality and endpoint health on Glama](https://glama.ai/mcp/connectors/io.github.alexblogoodf/glyfiq-medical-icons/badges/score.svg)](https://glama.ai/mcp/connectors/io.github.alexblogoodf/glyfiq-medical-icons)

## Connect (no account, no API key)

🔗 **Server URL:**  
https://glyfiq.link/mcp

[![Auth](https://img.shields.io/badge/Auth-No%20API%20Key%20Required-lightgrey?style=for-the-badge)](https://glyfiq.link/mcp)

---

>**Claude Code:** Settings, Connectors, Add Custom Connector, paste the URL.
>**ChatGPT and Codex:** Settings, Plugins, Add MCP Server, paste the URL.
>**Claude Desktop, VS Code, Windsurf, Zed:** add as a remote server.

---

## ✨ Tools
- **search_icons:** search by keyword or medical term
- **get_icon_svg:** SVG code by exact icon name
- **get_icons_svg:** batch SVG code for multiple icons (1 to 20)
- **list_tags:** top 50 medical tags
- **get_free_icons_sample:** random sample of free icons

**Add your license key:** https://glyfiq.link/mcp?license_key=YOUR_KEY

More at https://glyfiq.link

---

## 🔌 Quick Start (No Account, No API Key)

The free tier works instantly. Add the following configuration to your MCP client:

```json
{
  "mcpServers": {
    "glyfiq": {
      "url": "https://glyfiq.link/mcp"
    }
  }
}
