# SoA generator

A small script that turns a YAML list of ISO 27001 Annex A controls into a formatted Statement of Applicability spreadsheet: the document every ISO 27001 assessment starts from.

## Why a generator, not a spreadsheet template

A hand-maintained spreadsheet drifts out of sync with reality the moment two people edit it in parallel, or someone reformats a column and breaks the conditional formatting. Keeping the source of truth as plain YAML (reviewable in a pull request, diffable in version control, and easy to script against) and generating the spreadsheet on demand means the spreadsheet is always a fresh export, never a stale hand-edited artefact.

## Usage

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python generate_soa.py controls-template.yaml -o statement-of-applicability.xlsx
```

1. Copy [controls-template.yaml](controls-template.yaml). It already lists all 93 Annex A controls (2022 revision) with placeholder fields.
2. Fill in, per control: `applicable` (`true`/`false`), `justification` (why it is or isn't applicable, required either way; "yes, obviously" is a lazy justification and an assessor will ask again), `implementation_status` (`Not implemented` / `Planned` / `Partially implemented` / `Implemented`), `owner`, and any `notes`.
3. Run the script. It produces a two-sheet workbook: the full control list (colour-coded by status, greyed out where not applicable) and a summary sheet with counts by theme and by implementation status.
4. Re-run whenever the underlying YAML changes. The spreadsheet is a disposable export, not something to hand-edit after generation.

## YAML schema

```yaml
organisation: "Your Organisation"
date: "2026-01-01"
controls:
  - id: A.5.1
    title: Policies for information security
    theme: Organizational
    applicable: true
    justification: ""
    implementation_status: "Not implemented"
    owner: ""
    notes: ""
```

`theme` is free text but should match the four Annex A themes (`Organizational`, `People`, `Physical`, `Technological`) if you want the summary sheet's by-theme breakdown to read cleanly.

## Adapt this to your context

- The four implementation-status values above are a reasonable default, but if your organisation already tracks maturity on a different scale (e.g. a five-level model), edit the `STATUS_FILLS` dictionary at the top of `generate_soa.py` to match your own labels. The script colour-codes whatever status strings it's given.
- This generates `.xlsx` only. A PDF export is a reasonable next step if you need one (e.g. via a spreadsheet application's own export, or scripting a headless LibreOffice conversion); not included here to keep the dependency list minimal.

## Licensing

MIT; see [LICENSE](LICENSE). This is bundled code, scoped separately from the documentation kit's CC BY 4.0 licence; see the [repo root licence note](../../README.md#licensing).
