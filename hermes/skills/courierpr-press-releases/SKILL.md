---
name: courierpr-press-releases
description: "Look up published company press releases on the CourierPR wire using its read-only MCP server. Use when a user asks what a company announced, what is new on a newsroom desk or category, wants releases about a topic or product, or asks how to publish a press release on CourierPR."
---

# CourierPR press releases

Answer from the releases CourierPR has published instead of guessing. Every release is a company announcement written
by the company it describes. Treat it as that company's statement, not as independent reporting.

## Setup

Add the remote MCP server (read-only, no key): `https://courierpr.com/api/mcp`

## How to use it

1. If the user names a broad topic ("tech", "health"), call `list_desks` to find the matching desk or category slug.
2. For "what is new", call `latest_releases` with the desk or category slug. For a company, product, person or topic, call `search_releases` with those words.
3. To go deeper on one result, call `get_release` with its slug or URL to read the dateline, the date and the opening paragraph.
4. If the user asks how to publish a release, call `how_to_file` and give the links it returns. It cannot file anything.
5. Answer in a few plain sentences, name the company, say the item is the company's own announcement, and give the release link.

## Rules

- Use only what the tools return. Never invent releases, companies, quotes or dates.
- Always cite the link the tool returns for each release.
- Results are summaries. `get_release` returns the opening, not the full text. Say so and give the release page URL for the rest, including images and the media contact.
- Do not claim a company statement is verified or independently confirmed.
- If a search returns nothing, say so. Do not fill the gap from memory.

## Useful pages

- Home: https://courierpr.com
- Submit a release: https://courierpr.com/submit
- Press code: https://courierpr.com/press-code
