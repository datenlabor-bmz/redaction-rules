# Redaction Rules

A collection of structured redaction rules based on freedom of information (FOI) and transparency laws from various jurisdictions.

> **Disclaimer:** This is not an official legal source. While the rule texts are derived from official legal sources (linked in each rule file), this repository is provided for informational purposes only. Users should verify the accuracy and currency of the rules against the official sources before relying on them.

## Purpose

This repository provides machine-readable JSON files containing legal grounds for redacting information in public documents. Each rule includes the legal reference, a short description, and the full legal text.

## Data Sources

- **`de-ifg-bund.json`** — Created manually
- **All other rule sets** — Generated through research by Claude (claude-opus-4-5-20250514) based on official legal texts

## Usage

All available rule sets are listed in [`rules.json`](https://raw.githubusercontent.com/datenlabor-bmz/redaction-rules/main/rules.json), which provides direct links to each rule file.

## Available Rule Sets

| File | Jurisdiction | Law |
|------|--------------|-----|
| [`de-ifg-bund.json`](rules/de-ifg-bund.json) | 🇩🇪 Germany (Federal) | [Informationsfreiheitsgesetz (IFG)](https://www.gesetze-im-internet.de/ifg/) |
| [`us-foia.json`](rules/us-foia.json) | 🇺🇸 USA (Federal) | [Freedom of Information Act (FOIA)](https://www.law.cornell.edu/uscode/text/5/552) |
| [`uk-foi.json`](rules/uk-foi.json) | 🇬🇧 United Kingdom | [Freedom of Information Act 2000](https://www.legislation.gov.uk/ukpga/2000/36) |
| [`eu-1049.json`](rules/eu-1049.json) | 🇪🇺 European Union | [Regulation (EC) No 1049/2001](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32001R1049) |
| [`fr-cada.json`](rules/fr-cada.json) | 🇫🇷 France | [Code des relations entre le public et l'administration (CRPA)](https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000031366350/LEGISCTA000031367696/) |

## Schema

Each rule file contains metadata about the law and an array of exemption rules:

```json
{
  "metadata": {
    "jurisdiction": "ISO country code (e.g. DE, US, GB, EU, FR)",
    "jurisdiction_name": "Full name of the jurisdiction",
    "law_name": "Official name of the law (in native language)",
    "law_name_en": "English name (if different from native)",
    "abbreviation": "Common abbreviation (e.g. IFG, FOIA)",
    "enacted": "Date enacted (YYYY-MM-DD)",
    "last_amended": "Date of last amendment (YYYY-MM-DD or null)",
    "version_date": "Date this ruleset reflects",
    "official_url": "Link to official legal source",
    "oversight_body": "FOI oversight authority",
    "language": "Language code of rule text (e.g. en, de, fr)",
    "scope": "What the law covers"
  },
  "rules": [
    {
      "group": "Category of the exemption",
      "title": "Short title",
      "reference": "Legal reference (e.g. §3 Nr. 1)",
      "reason": "Brief description of the redaction reason",
      "full_text": "Complete legal text of the provision",
      "url": "Link to the official legal source"
    }
  ]
}
```

Some jurisdictions may include additional rule fields. For example, UK FOI and EU 1049/2001 exemptions include a `type` field indicating whether the exemption is "absolute" (no public interest test required) or "qualified" (public interest test applies).

## Contributing

Additional rule sets for other jurisdictions are welcome. Please:

1. Add your rule file to the `rules/` folder using the naming convention: `{country-code}-{law-abbreviation}.json`
2. Update `rules.json` to include the new rule set

## License

CC0 1.0 Universal
