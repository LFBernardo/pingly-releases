# Changelog

User-facing release notes for Pingly. Each release is also tagged on the
[Releases page](https://github.com/LFBernardo/pingly-releases/releases),
where you'll find installers for macOS, Linux, and Windows.

## v1.0.1 — 2026-06-22

### New

- **Resume a stopped trace.** Click `▶ Resume` next to the new `⨯ Dismiss`
  button to pick up probing on a target you previously stopped. The hop
  table, sparklines, and historical samples carry over — no need to start
  a fresh trace and lose the data you'd collected.

### Changed

- **Stop now preserves your data.** Previously, stopping a target wiped its
  persisted samples and hops, which meant you couldn't come back to it
  later. Stopped targets now stay in the sidebar across app restarts and
  reappear with their last-seen route, ready to Resume.
- **Dismiss is the destructive button** — it's what removes the target and
  wipes everything for it. Use Stop if you might want the trace back.

### Upgrade notes

- Existing workspaces upgrade in place — no manual migration needed.
- Any traces you stopped in **v1.0.0** are gone (Stop deleted them at the
  time). Traces stopped from **v1.0.1** onward will persist as described.

## v1.0.0 — 2026-06-22

First stable release. Native desktop app for **macOS arm64**, **Linux x64**,
and **Windows x64**.

### Highlights

- Multi-target ICMP traceroute with continuous per-hop pinging
- Live destination timeline with monotone-cubic smoothing that still
  preserves sharp packet-loss spikes
- Geographic route map — click to expand to a full-window view
- Double-click any hop to spawn it as a nested sub-target in the sidebar
- Alert engine: loss / RTT / jitter / target-down / route-changed, with
  desktop notifications and Slack/Discord-compatible webhooks
- Headless `pingly-probe` CLI with NDJSON output mode
- Local SQLite persistence with configurable retention (default 30 days)

See the [README](README.md) for download and install instructions.
