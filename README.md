# CourierPR MCP server

A public, read-only [Model Context Protocol](https://modelcontextprotocol.io) server for
[CourierPR](https://courierpr.com), a press release wire. Companies file releases, and each one is published as a
permanent article on courierpr.com, organised into six newsroom desks and twenty categories. This server lets an
assistant browse the desks, list the newest releases, search them and read the opening of one.

Releases are company announcements written by the company they describe. They are the company's own statement, not
independent reporting. The data here is what the site publishes.

- **Server URL:** `https://courierpr.com/api/mcp`
- **Transport:** Streamable HTTP, stateless
- **Authentication:** none
- **Access:** read-only. Nothing is written, and no release can be filed through it.

## Tools

| Tool | What it does |
|---|---|
| `list_desks` | The six newsroom desks and the twenty categories under them, with slugs and links. Use it to resolve a topic the user named ('tech', 'health') into a desk or category before calling latest_releases. Returns no releases. |
| `latest_releases` | The newest published press releases, optionally within one desk or one category. Each result is a title, company, date, short summary and a link. At most 10 per call, newest first, no date filter. |
| `search_releases` | Full-text search over every published press release (title and body), optionally within one category. English full-text matching, at most 10 results, no date filter. |
| `get_release` | One published press release by slug or full courierpr.com URL: title, company, category, dateline, date, the opening 120 words and a link to the full release. A summary, not the full text; media contact details are never included. |
| `how_to_file` | What filing a release on CourierPR involves: what is accepted (the press code) and the links to file, for agencies and for journalists. Returns links only; it does not file anything. |
| `search` | Connector-style search over published press releases. Returns ids for fetch. Prefer search_releases when you can filter by category. |
| `fetch` | Connector-style fetch of one press release by the id from search. Same summary as get_release. |

Each result is a short summary or the opening of a release with a link to the full page, where the full text,
images and media contact are.

## Add it to your client

Add the server URL `https://courierpr.com/api/mcp` as a remote MCP server (Streamable HTTP, no key needed).

## Example questions

- What is new on the Science & Tech desk?
- Search CourierPR for releases about electric vehicles.
- Which categories does CourierPR cover?
- How do I publish a press release on CourierPR?

## Links

- Home: https://courierpr.com
- Submit a release: https://courierpr.com/submit
- Press code: https://courierpr.com/press-code
- For agencies: https://courierpr.com/for-agencies
- For journalists: https://courierpr.com/for-journalists
- Privacy: https://courierpr.com/privacy
- Terms: https://courierpr.com/terms

## Hermes plugin

The `hermes/` folder holds a Hermes plugin (`plugin.json`, `mcp.json`) and one skill, `courierpr-press-releases`,
that tells an agent how to use these tools.
