# KringleCrate Administrator Guide

## Installation Checklist
- **Server version:** Built for Minecraft/Paper 1.21 (see `api-version` in `plugin.yml`).
- **Economy (optional):** Install Vault and a compatible economy plugin to enable currency gifts. Without Vault, item gifts still work and the plugin warns players that currency is unavailable.
- **Deploy:** Place the compiled JAR in `plugins/`, start the server once to generate default config files.

## Configuration
KringleCrate reads its schedule from `config.yml` in the plugin data folder.
```yaml
redemption-start: "2024-12-25T00:00:00"
redemption-end: "2025-01-01T23:59:59"
reveal-date: "2024-12-20T00:00:00"
```
- Use ISO-8601 local date-time format (`YYYY-MM-DDTHH:MM:SS`). Invalid entries fall back to safe defaults and log errors.
- Players cannot join during the redemption window, and gift submission is only allowed after the reveal date and before redemption begins.
- Redemption is only permitted between `redemption-start` and `redemption-end`.

## Permissions
- `kringlecrate.redeem` — Allows `/kc redeem` (defaults to `true`).
- `kringlecrate.override` — Lets staff bypass the reveal date when using `/kc reveal`.

## Data Files
- `gifts.yml` — Stores participants, assignments, wishlists, and queued gifts.
  - Participants are recorded under `participants`.
  - Pairings are saved under `assignments.<giverUUID> = <recipientUUID>`.
  - Wishlists live under `wishlists.<playerUUID>`.
  - Gifts accumulate under `gifts.<recipientUUID>` with sender metadata and item or currency data.
- The file is saved after every change; back it up before wiping or migrating events.

## Event Operations
1. **Set the dates** in `config.yml`, then reload or restart the server.
2. **Announce joining** — players opt in with `/kc join` (blocked during redemption).
3. **Monitor participants** — assignments are generated automatically the first time a player uses `/kc reveal` after enough players have joined (minimum of two).
4. **Encourage gifting** — players can submit items or currency after the reveal date but before redemption starts.
5. **Redemption** — during the redemption window, `/kc redeem` moves stored items into inventories and deposits any currency gifts via Vault.

## Troubleshooting
- **Assignments missing:** Ensure at least two participants exist; the plugin logs an error and skips assignment otherwise.
- **Economy unavailable:** If Vault or an economy provider is missing, currency gifting and redemption are blocked; players receive guidance to contact staff.
- **Inventory space errors:** Ask players to clear slots before redeeming; the plugin refuses to drop items on the ground.
- **Date format errors:** Check the server console for config parsing warnings; fix the timestamps and reload.
