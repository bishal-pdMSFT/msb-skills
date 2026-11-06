---
name: notebooklm-ops
description: Operate Google NotebookLM MCP authentication lifecycle on Linux host. Use for NotebookLM MCP (`notebooklm-mcp` via `mcporter`) when cookies expire frequently and auth must be refreshed often. Handles on/off, auth refresh, status, and smoke test. Triggers: "Включи NotebookLM", "Выключи NotebookLM", "обнови авторизацию NotebookLM", "проверь NotebookLM".
---

# NotebookLM Ops

Automate operations for **NotebookLM MCP** in environments where Google session cookies become invalid quickly.

This skill solves repeated manual auth refresh by automating:
- GUI stack startup,
- navigation to NotebookLM,
- auth refresh via CDP,
- MCP sanity checks,
- full cleanup on shutdown.

Run commands from `[REDACTED_ABSOLUTE_PATH]`.

## Requirements / dependencies

- Linux host with Chromium and CDP (`--remote-debugging-port=9222`).
- Virtual display stack: **Xvfb + openbox + x11vnc**.
- Working scripts used by this skill:
  - `[REDACTED_ABSOLUTE_PATH]`
  - `[REDACTED_ABSOLUTE_PATH]`
  - `[REDACTED_ABSOLUTE_PATH]`
  - `[REDACTED_ABSOLUTE_PATH]`
- NotebookLM MCP configured in `mcporter` (`notebooklm-mcp`).

## One-time login

A one-time manual login in Chromium to Google/NotebookLM is required.
After that, this skill keeps refresh automated by reusing the same browser profile/session.

## Turn NotebookLM ON

Execute:

```bash
[REDACTED_ABSOLUTE_PATH]
```

Required sequence:
1. Start GUI/CDP stack (Xvfb + openbox + x11vnc + Chromium).
2. Navigate the **current tab** to `https://notebooklm.google.com/`.
3. Wait for load.
4. Refresh NotebookLM auth via CDP.
5. Reload NotebookLM MCP auth and run sanity check (`notebooklm-list`).

## Turn NotebookLM OFF

Execute:

```bash
[REDACTED_ABSOLUTE_PATH]
```

Stop Chromium and related GUI processes (x11vnc/Xvfb/openbox), then clean leftovers.

## Check status

Execute:

```bash
[REDACTED_ABSOLUTE_PATH]
```

## Smoke test

Execute:

```bash
[REDACTED_ABSOLUTE_PATH]
```

Expected result: notebook list returns `"status": "success"`.

## Failure handling

If auth refresh fails:
1. Re-run NotebookLM ON once.
2. If still failing, ask user to log in at `https://notebooklm.google.com/` in the same Chromium profile via VNC.
3. Re-run NotebookLM ON and smoke test.
