# tugui-specs-data

Marketplace product photo specs for **18 platforms / 51 rules**, each rule carrying the URL it was checked against.

- `specs.json` — full dataset (`version`, `generatedAt`, `license`, `source`, `platforms[].rules[]`)
- `specs.csv` — the same rules flat, one row per rule

Machine-readable copies are also served at <https://tugui.top/data/specs.json> and <https://tugui.top/data/specs.csv>;
the human-readable pages are <https://tugui.top/platforms/> and <https://tugui.top/size/>.

`generatedAt` is the date the source pages were last checked by hand — not the date this file was regenerated.
Where a rule only has a third-party write-up behind it, `sourceKind` says so; nothing here is a guess about a
platform's live upload rules. Re-running the exporter is what produces these files:

```bash
node ops/gen-public-data.mjs   # writes app/public/data/specs.{json,csv}
```

## Shape

```json
{
  "version": 1,
  "generatedAt": "2026-10-25",
  "license": "MIT",
  "source": "https://tugui.top/platforms/",
  "platforms": [
    {
      "id": "taobao", "name": "...", "nameEn": "...", "region": "CN", "homepage": "...",
      "sourceUrl": "...", "sourceKind": "official",
      "rules": [
        { "id": "white-800", "slot": "main", "labelEn": "...", "width": 800, "height": 800,
          "aspect": "1:1", "minWidth": 800, "maxKB": null, "background": "white",
          "formats": ["jpg", "png"], "notesEn": "...", "sourceUrl": "..." }
      ]
    }
  ]
}
```

## Licence

MIT for this dataset file. The platform names are trademarks of their owners; this is a convenience copy of
publicly documented upload requirements, not an endorsement or an official API.

Maintained by Tugui — <https://tugui.top/> — 19211363741@163.com
