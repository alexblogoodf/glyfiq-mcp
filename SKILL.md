---
name: glyfiq-icons
description: Find and insert hand-drawn medical and health SVG icons from the Glyfiq library via its MCP server (tools search_icons, get_icon_svg, get_icons_svg, list_tags). Use this skill whenever the user needs an icon, pictogram or illustration for anything medical, health, healthcare, clinical, anatomy, pharmacy, diagnostics or wellness (heart, lungs, MRI, stethoscope, fracture, vaccine, pill, patient, clinic and similar), for a website, app, slide, UI mockup, infographic or document, even if they never mention Glyfiq. Prefer this over drawing SVG paths yourself or guessing icon names.
---

# Glyfiq medical icons

Glyfiq is a library of hand-drawn medical and health icons (each with detailed medical tags), exposed through an MCP server. Use it so that icons are real, consistent and never generated or invented by the model.

## Rules

1. Never write or "improve" icon SVG paths yourself, and never invent an icon name. Every name must come from `search_icons` results.
2. Always search first, then fetch the SVG. `search_icons` returns metadata only (name, tags, `is_free`), never SVG code.
3. Copy the SVG returned by the tool without altering its paths. Only the attributes listed in "Styling" may be changed.
4. Respect licensing. See "Free vs PRO".

## Workflow

1. **Search.** Call `search_icons` with a short medical term (`query`, up to 100 characters). Use `limit` 5-10 for a quick lookup and up to 50 for a broad scan. If results are poor, try a synonym or a more general term, or call `list_tags` to pick a better term.
2. **Choose.** Pick the best match by its name and tags. If several fit, prefer the one whose tags match the user's context.
3. **Check `is_free`.** If the best match has `is_free: false`, see "Free vs PRO" before fetching.
4. **Fetch.**
   - One icon: `get_icon_svg` with the exact `name`.
   - Two or more: a single `get_icons_svg` call with up to 20 exact names. Each result comes back as `ok`, `premium_locked` or `not_found`.
5. **Insert** the SVG where the user needs it (inline in HTML or JSX, a standalone `.svg` file, a slide, and so on) and apply the styling below.

Icon names are exactly as returned by search. They can contain spaces and mixed case (for example `heart MRI`, `diagnostics and stethoscope`), so do not convert them to kebab-case or change their capitalization.

## SVG format and styling

- Every icon is a 256 x 256 `viewBox`, outline style: `fill="none"`, `stroke="#000000"`, `stroke-width="8"`, round caps and joins.
- Resize by changing `width` and `height` on the root `<svg>`. Keep the `viewBox` unchanged.
- Colors are hardcoded to `#000000`. To make an icon follow the text color or a theme, replace `stroke="#000000"` with `stroke="currentColor"`, or set the color you need. Do not add a fill.
- For small sizes (below about 24 px) the 8 px stroke gets thick relative to the icon. Mention this if the user wants tiny icons, and do not change `stroke-width` unless they ask.
- When using several icons together, keep the same size and stroke color for all of them so the set stays visually consistent.
- For accessibility, add `role="img"` and `aria-label` for meaningful icons, or `aria-hidden="true"` for decorative ones.

## Free vs PRO

- Free icons work without a key. PRO icons are listed in search with `is_free: false` and require a license key.
- The free tier is intended for personal use and evaluation. A commercial use license comes with PRO. If the user's project looks commercial, tell them to check the Glyfiq license terms (https://glyfiq.link) before shipping.
- If a needed icon is PRO and the connection has no key (`premium_locked` or an upgrade message):
  1. Do not substitute a hand-drawn or generated SVG for it.
  2. Tell the user the icon requires PRO, and offer the best free alternatives from the same search.
  3. If they want PRO: https://blogoodf.gumroad.com/l/glyfiq. The same key works for the MCP server and the Figma, Framer and Illustrator plugins.
- Never ask the user to paste a license key into chat, and never write a key into code, commits or shared files. The key belongs in the connector configuration (see Setup).

## Troubleshooting

- **Not found:** the name was not exact. Run `search_icons` again and use the name from the results.
- **No good match:** broaden the query, try an English synonym or a Latin or clinical term, or check `list_tags`. If the library truly has no match, say so and suggest the closest alternatives instead of inventing one.
- **Tools unavailable:** the MCP server is not connected. See Setup.
- **Wrong or broken icon:** ask the user to report the icon name at https://github.com/alexblogoodf/glyfiq-mcp.

## Setup (only if the Glyfiq tools are not available)

The server is a remote Streamable HTTP MCP server, no account needed for the free tier:

```
https://glyfiq.link/mcp
```

- Claude Code: `claude mcp add glyfiq --transport http https://glyfiq.link/mcp`
- Other clients (Claude Desktop and Claude.ai custom connectors, ChatGPT, VS Code, Cursor, Windsurf, Zed): add it as a custom or remote MCP server with the URL above. Exact menus differ by client and version; see https://glyfiq.link.
- PRO: use `https://glyfiq.link/mcp?license_key=YOUR_KEY` as the connector URL, then reconnect. The key is secret, so do not commit it to a repository or share screenshots of the URL.
