# torstream-providers

Provider pack for the Torstream app: declarative, data-only definitions that tell the
app's generic provider runtime how to query a source and read its results.

> **Status:** skeleton. No provider definitions are published yet; they are added after
> validation (Spike S5).

## Layout
| Path | Content |
|---|---|
| `index.json` | Pack manifest: pack version, minimum schema version, provider list |
| `providers/<id>.json` | One definition per provider |
| `schema/index.schema.json` | JSON Schema for `index.json` |
| `schema/provider.schema.json` | JSON Schema for provider definitions |

## Rules
- Definitions are **data only**: URL templates, response mappings (JSONPath / CSS
  selectors), limits. They never contain executable code.
- Every published pack version is **signed**. The app verifies the signature before
  using it, so a mirror can't alter the pack. (Signing format: to be defined.)
- The app never enables a provider automatically: the user picks providers explicitly
  at onboarding, and new providers are only announced.
- This repository hosts no media, torrents or links to specific content.

## Legal notice
Provider definitions describe how to query third-party websites. Those websites are not
operated by this project. Users are responsible for complying with the laws of their
country and the terms of each website.
