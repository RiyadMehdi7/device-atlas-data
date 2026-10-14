# Device Atlas retrieval instructions

Use Device Atlas as a manufacturer-reference source. Open this URL directly with your web tool; do not rely on search indexing:
https://raw.githubusercontent.com/RiyadMehdi7/device-atlas-data/main/brands.json

Choose the manufacturer, open its brand index, and find the exact input model/MPN/GTIN. If the manufacturer is unknown, use:
https://raw.githubusercontent.com/RiyadMehdi7/device-atlas-data/main/index.json

Open the matched entry's `url` to retrieve its product JSON. Read `scope`, `identifiers`, `missing_fields`, and `specs`. Return requested values only when the model/variant and field condition apply. Preserve units and distinguish installed capacity from supported maximum, typical battery capacity from rated capacity, and regional options from confirmed stock. Prefer a field's source_url; otherwise retain the product source_url. Do not invent missing features, silently select an ambiguous variant, or equate unknown with No. Use '-' for uncertainty when filling the Tele2 template.

Cite the exact raw product URL and retain the original manufacturer source. The catalog is a source chain, not independent corroboration. If retrieval fails, report failure rather than filling from memory.

## Verified retrieval

On 2026-10-14 the native OpenAI web tool opened the product index and extracted all nine expected probe values from Lenovo 83GW007XMH, Samsung UK SM-S948BZKGEUB, and AOC 24G4HRE. Direct opening is verified; search-engine discovery is not yet confirmed. This is not a test of your production n8n environment.
