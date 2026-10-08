# Gede'uffa AI Language System

A rule-aware, incrementally extensible English-to-Gede'uffa research foundation. The repository starts with transparent dictionary import and data-driven linguistic rules; it does not infer missing grammar or silently choose among conflicting dictionary forms.

## Quick start

```bash
python3 scripts/validate_dictionary.py /path/to/english_amharic_gedeuffa_clean.csv
python3 scripts/import_dictionary.py /path/to/english_amharic_gedeuffa_clean.csv
python3 -m unittest discover -s tests
python3 scripts/evaluate.py
```

The input CSV is read only. Normalized entries are written under `data/processed/`. Supported source headers include `English_Root_Word`/`Amharic_Translation`/`Gede_uffa_Translation` and `English`/`Amharic`/`Gede_uffa`. Use `--output` to choose another destination.

## Current scope

The importer preserves alternative translations, records missing metadata as null/empty, and emits a report for structural issues. The dictionary service supports lookup by English, Amharic, or Gede'uffa. A small deterministic English parser and data-driven generation path demonstrates how syntax, grammar, and morphology remain separate. The supplied example rules are provisional knowledge, not a complete grammar. Unsupported constructions return unresolved items instead of invented forms.

See [architecture](docs/architecture.md), [dictionary format](docs/dictionary.md), [rule guide](docs/adding-rules.md), and [linguistic notes](docs/grammar.md).
