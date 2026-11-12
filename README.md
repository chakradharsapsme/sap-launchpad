# SAP Consultant Launchpad

A single page that gathers the official SAP sources an SAP consultant or architect
actually opens in a week — Help Portal, Community, SAP for Me, Discovery Center,
the Business Accelerator Hub, Ariba and Next-Gen Ariba, S/4HANA, BTP, the AI
portfolio and the integrated toolchain — grouped, searchable, and sitting beside
short learning outlines.

**56 tiles across 7 groups, plus 5 guides.** No build step, no dependencies, no
tracking. One HTML file.

## What's in it

| Group | Covers |
|---|---|
| Learning | SAP Learning, journeys, certification, practice systems, live sessions, Discovery Center, Road Map Explorer |
| Community & Support | SAP Community, SAP for Me, Notes & KBAs, software downloads, Guided Answers, Trust Center |
| BTP & Development | Developer Center, Business Accelerator Hub, BTP cockpits, Integration Suite, SAP Build, SAP samples |
| Ariba | Next-Gen SAP Ariba, Help Portal, Ariba Connect, Business Network, supplier enablement, three learning journeys |
| S/4HANA & Process | Process Navigator, Fiori Apps Reference Library, release docs, Readiness Check |
| AI & Data | SAP Business AI, Joule, Joule for Consultants, HANA Cloud, Datasphere, Analytics Cloud |
| Architecture & Toolchain | Architecture Center, Signavio, LeanIX, Cloud ALM |

The five guides are written outlines rather than links, opening in a side panel:

- **Next-Gen Ariba, explained** — what was rebuilt, Intake Management, the Icertis
  contract integration, the Bid Analysis Agent, and what a migration involves
- **What to learn in BTP** — the platform in five layers, in build order
- **Integration mechanisms** — IDoc, OData, SOAP, REST, events, and when to reach
  for each
- **Source-to-Pay landscape** — upstream, downstream, network, and the integration
  between them
- **Clean core, explained** — the four extensibility tiers and how to decide where
  a change belongs

## Using it

Open `index.html` in a browser. That's the whole thing.

- `/` or `Ctrl`/`Cmd`+`K` focuses search; `Esc` clears it
- The left rail filters by group; the hamburger opens it on a phone
- Star any tile to keep it under **Pinned** (stored in that browser only)
- The ◐ button switches light and dark; it also follows your system theme

## Publishing it on GitHub Pages

1. Create a new public repository — `sap-launchpad` is a good name.
2. Upload `index.html` and `README.md` to the root (drag and drop works:
   **Add file → Upload files**).
3. **Settings → Pages**. Under *Build and deployment*, set **Source** to
   *Deploy from a branch*, **Branch** to `main` and the folder to `/ (root)`.
   Save.
4. Wait a minute or two. The site appears at
   `https://<your-username>.github.io/sap-launchpad/`.

GitHub Pages needs a public repository on the free plan. Nothing in this page is
private — no credentials, no personal links, no analytics — so it is safe to
publish as it stands.

## Changing the tiles

Everything is data at the top of the `<script>` block in `index.html`.

A tile:

```js
{ cat:'ariba', ic:'doc', name:'Ariba Help Portal',
  desc:'Sourcing, Contracts, Buying, Invoicing and Network docs.',
  url:'https://help.sap.com/docs/ariba',
  tags:'documentation sourcing buying invoicing' },
```

- `cat` — which group it belongs to, from the `CATS` list
- `ic` — an icon name from the `SVG` set at the top of the script
- `tags` — extra words the search should match; they are not displayed
- `big: true` — makes the tile double width
- `hl: true` with `hue` and `alt` — highlights it, as the events tile does
- `tag:'Course'` — adds a small chip in the tile footer

Add a group by appending to `CATS` and defining its two colour tokens in each of
the three `:root` blocks in the stylesheet (light, `prefers-color-scheme: dark`,
and `[data-theme="dark"]`).

## Notes

Every tile links out to an official SAP site. Nothing is mirrored or rehosted
here, and no SAP documents, diagrams or images are included.

Not affiliated with or endorsed by SAP SE. SAP, SAP S/4HANA, SAP Ariba, SAP BTP,
Joule, Signavio and LeanIX are trademarks of SAP SE.

Curated by Chakradhar Nannapaneni.
