---
name: creai-prompts
description: Create interactive prompts for a YouTube video with Creai. Use when the user wants to generate, review, publish or share Creai prompts for a video on their own channel.
---

Work through these steps in order, using the Creai connector's tools.

1. Call `list_workspaces`. Use the only workspace, or ask which one.
2. Call `get_connection_status`. If the YouTube channel is not connected, give the console link it returns and stop.
3. Call `list_videos` and confirm with the user which video they mean.
4. Call `get_allowance` and tell the user how many generations remain before starting.
5. Call `start_generation` only when the user explicitly asks for it. Then poll `get_generation_status` until it finishes.
6. Call `list_generations` and show the pack text so the user can review it.
7. Call `make_live` only after the user says to publish. It changes what viewers see.
8. Call `get_watch_link` and give the link to the user.

Rules:

- Work on the user's own channel only. Never help bypass channel ownership.
- Never invent video ids or workspace ids. Use values the tools returned.
- Report errors as the tool returned them.
