# Glyfiq Icon Library for AI Agents

Hand-drawn medical and health icons for AI agents. Search by medical terminology and get clean SVG code — no AI-generated paths, no hallucinated icon names.

## Quick Setup (Free, No Account Required)

Choose your AI client and follow the steps:

### Claude Code

```bash
claude mcp add glyfiq --transport http https://glyfiq.link/mcp
```

### ChatGPT & Codex

1. Settings → Plugins → Add MCP Server
2. Server URL (No Authentication): `https://glyfiq.link/mcp`
3. Create as plugin → Connect Glyfiq

### Claude Desktop, VS Code, Cursor, Windsurf, Zed

Add as a remote Streamable HTTP server:

```
https://glyfiq.link/mcp
```

### PRO Version (Full Library Access)

Replace the URL with your license key from Gumroad:

```
https://glyfiq.link/mcp?license_key=YOUR_KEY
```

## How to Use Glyfiq

### 1. Search for icons
Call `search_icons` with a medical term:
- "Find me cardiology icons"
- "Search for MRI scanner icons"
- "Look up fracture and bone healing icons"

### 2. Get the SVG code
Use `get_icon_svg` with the exact name from search results:
- "Get the SVG for 'heart-anatomy'"
- "Fetch the SVG code for 'stethoscope'"

### 3. Batch fetch multiple icons
Use `get_icons_svg` to get up to 20 icons at once:
- "Get SVGs for 'heart', 'lungs', 'brain' in one call"

### 4. Explore the library
- `list_tags` — see the top 50 most common medical tags
- `get_free_icons_sample` — preview random free icons

## Free vs PRO

**Free tier** (no key needed):
- Search the entire library
- Get SVG code for all free icons
- Browse popular tags
- Perfect for personal projects and evaluation

**PRO tier** (license key required):
- Full SVG access to all icons
- Commercial use license
- Priority support
- One key unlocks MCP + Figma + Framer + Illustrator

## When You Need PRO Icons

If you search for an icon and see it marked as `is_free: false`, you'll see:

```
🔒 Icon "X" is premium.

Get Glyfiq PRO to access:
https://blogoodf.gumroad.com/l/glyfiq

To unlock, add ?license_key=YOUR_KEY to the connector URL.
```

**What to do:**
1. Buy PRO at https://blogoodf.gumroad.com/l/glyfiq
2. Copy the license key from your Gumroad receipt
3. Update your MCP connector URL:
   - Replace: `https://glyfiq.link/mcp`
   - With: `https://glyfiq.link/mcp?license_key=YOUR_KEY`
4. Reconnect or restart your client

One key works everywhere — MCP server, Figma plugin, Framer plugin, Illustrator plugin.

## Why AI Agents Design with Glyfiq

✅ **No invented icon names** — every icon has a precise definition and medical tags
✅ **No AI-generated SVGs** — every icon is hand-drawn by the author
✅ **One consistent style** — visual coherence across your entire project
✅ **1,000+ icons now, 6,000+ roadmap** — your agent finds real matches, not "close enough"
✅ **Free for personal use** — try before you buy
✅ **No API key for free tier** — point and use, nothing to sign up for

## Troubleshooting

**"Icon not found" error:**
The exact name doesn't exist. Call `search_icons` again with broader terms or check `list_tags` for the right medical terminology.

**"License key not provided" for PRO icons:**
You're using the free connector URL. Update it with your license key from Gumroad.

**Icons look wrong or low quality:**
This shouldn't happen — all icons are hand-drawn at 256×256 viewBox. Report the issue with the icon name.

## Support

- Full documentation: https://glyfiq.link
- GitHub: https://github.com/alexblogoodf/glyfiq-mcp
- Twitter/X: @AlexBlogoodf
- Telegram: @blogoodf

For custom icon requests or enterprise licensing, contact through the website.