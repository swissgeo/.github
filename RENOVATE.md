# Renovate Preset

This preset was created for a Tech Talk and DEMO of Renovate.

## Usage

Add this to your repository's `renovate.json`:

```json
{
  "extends": ["github>swissgeo/.github:renovate-preset/default.json5"]
}
```

To extend from a specific branch, use the `#` syntax:

```json
{
  "extends": ["github>swissgeo/.github:renovate-preset/default.json5#feat_GPS-431_renovate_preset"]
}
```
