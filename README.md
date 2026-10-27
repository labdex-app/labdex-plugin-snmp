# SNMP neighbours

A [labdex](https://github.com/reykimedev/labdex) plugin. Reads switches and routers over SNMP (v2c or v3) — who sits on which port, from LLDP and Cisco's CDP — and suggests those cables on the Cables page. Also reports whether each one answers. Read-only. Applies to hosts tagged snmp to start with.

**Version** 1.0 · **Works with** labdex >=1.20,<2 · **Plugin id** `snmp`

> [!WARNING]
> Built with AI, for home labs only: labdex and its plugins were written largely with an AI
> coding assistant (Claude), directed and reviewed by a human. They haven't had an independent
> security audit and may contain security problems. Run them on a trusted home network.

## Install

It ships with labdex: **Plugins › Marketplace**, then *Install* (nothing is downloaded). Updates arrive through the official Marketplace (signed with the labdex project key).

## Settings

| Setting | Notes |
| --- | --- |
| SNMP version |  |
| Community | Read-only community, often public; pick it from the vault to share it |
| User |  |
| Authentication |  |
| Authentication passphrase |  |
| Privacy | AES-128 |
| Privacy passphrase |  |
| Port |  |
| Timeout (seconds) |  |

## Actions

- **Check the switches** (run): Asks each host it applies to for its name
- **Read neighbours** (run): LLDP and CDP neighbours of every host it applies to; new cables show on the Cables page

## Releasing

Bump `version` in `plugin.yaml`, add a `## <version>` section to `CHANGELOG.md`, commit, then
`git tag v<version> && git push --tags`. The release workflow signs the plugin with the
`LABDEX_SIGNING_KEY` secret and attaches `snmp-<version>.zip` to a GitHub release.
