# Device Atlas data

Public manufacturer-reference JSON for 1,106 product/variant records and 57,036 specification entries.

Fetch [index.json](index.json), match an exact model or identifier, then fetch the referenced product JSON. Every product preserves specifications, units, conditions, source URLs, regional scope and uncertainty metadata. Manufacturer claims are not independent laboratory verification. Unknown does not mean No.

No API key or GitHub API is required. Read files over ordinary HTTPS from `https://raw.githubusercontent.com/RiyadMehdi7/device-atlas-data/main/`.

Examples:
- [Lenovo V15 G5 IRL — 83GW007XMH](products/lenovo-83gw007xmh.json)
- [Samsung Galaxy S26 Ultra — UK variant SM-S948BZKGEUB](products/samsung-galaxy-s26-ultra-uk-manufacturer-variant-sm-s948bzkgeub.json)
- [AOC 24G4HRE](products/aoc-24g4hre.json)

The main catalog is https://device-atlas-catalog.netlify.app/ . Search-engine discovery and native OpenAI web-tool availability require separate verification; ordinary HTTP access is not proof of either.

## Agent retrieval contract

1. Fetch index.json by HTTPS GET.
2. Match manufacturer and exact MPN/GTIN when supplied. If multiple variants match, retain the ambiguity rather than choosing one silently.
3. Fetch only the selected products/{id}.json URLs.
4. Extract existing specs[].label/value/unit/condition and field-level source metadata. Where a field lacks its own source, retain the product source URL.
5. Preserve scope and uncertainty. Do not convert supported maximum capacity to installed capacity. Do not transfer regional SKU facts to another configuration.
6. Return missing or uncertain values as unknown (or '-' when the target template requires it).

These public artifacts exclude authenticated Icecat downloads, credentials and private workspace files. Original source rights remain with their respective owners; no blanket license to source materials is asserted.
