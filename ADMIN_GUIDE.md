# KringleCrate Administration Guide

This guide provides administrators with the information needed to configure and manage the KringleCrate plugin.

## Configuration

The main configuration for the plugin is handled in `config.yml`. Here are the available options:

```yaml
redemption-start: "2024-12-25T00:00:00"
redemption-end: "2025-01-01T23:59:59"
reveal-date: "2024-12-20T00:00:00"
```

*   `redemption-start`: The date and time when players can start redeeming their gifts.
*   `redemption-end`: The date and time when the redemption period ends.
*   `reveal-date`: The date and time when players can use the `/kc reveal` command to find out who their recipient is.

## Permissions

The following permissions are available for administrators:

*   `kringlecrate.override`: Allows an administrator to bypass the `reveal-date` restriction and use the `/kc reveal` command at any time. This is useful for testing or for situations where an early reveal is necessary.
*   `kringlecrate.redeem`: Grants access to the `/kc redeem` command. This permission is enabled for all players by default.
