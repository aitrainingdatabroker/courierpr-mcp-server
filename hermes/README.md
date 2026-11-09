# CourierPR for Hermes

Adds the public, read-only [CourierPR](https://courierpr.com) MCP server and one skill that tells the agent how to
use it. CourierPR is a press release wire with six newsroom desks and twenty categories. Ask what a desk published
lately, search releases by company or topic, read the opening of one, or find out how a release is filed. Every
release is a company announcement written by the company it describes, not independent reporting.

- **Server:** `https://courierpr.com/api/mcp` (Streamable HTTP, no key, no sign-in)
- **Disclosure:** every tool call goes to courierpr.com. The tools only read published releases. Nothing is written, no key is needed, and no local commands are run. No telemetry beyond ordinary server logs. Only configuration and a skill are installed. The tool list is served by the remote server at runtime and is not covered by the pinned commit.
- **Skill:** `skills/courierpr-press-releases`

More links: [home](https://courierpr.com), [submit a release](https://courierpr.com/submit), [press code](https://courierpr.com/press-code).
