# torstream-providers

Provider pack for the Torstream app: declarative, data-only definitions that tell the
app's generic provider runtime how to query a source and read its results.

> **Status:** pack version 1 (2026-10-27): The Pirate Bay (API) and SubsPlease, validated in
> Spike S5 and in the app's tests.

## Layout
| Path | Content |
|---|---|
| `index.json` | Pack manifest: pack version, minimum schema version, provider list with each definition's SHA-256 |
| `index.json.sig` | Ed25519 signature over `index.json` (base64) |
| `providers/<id>.json` | One definition per provider |
| `schema/index.schema.json` | JSON Schema for `index.json` |
| `schema/provider.schema.json` | JSON Schema for provider definitions |

## Rules
- Definitions are **data only**: URL templates, response mappings (JSONPath / CSS
  selectors), limits. They never contain executable code.
- Every published pack version is **signed** (Ed25519 over `index.json`, which lists the
  SHA-256 of every definition). The app verifies the signature with keys built into it,
  refuses older pack versions, and checks each definition's hash, so a mirror can't alter
  the pack.
- The app never enables a provider automatically: the user picks providers explicitly
  at onboarding, and new providers are only announced.
- This repository hosts no media, torrents or links to specific content.

## Legal notice
Provider definitions describe how to query third-party websites. Those websites are not
operated by this project. Users are responsible for complying with the laws of their
country and the terms of each website.
