---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Configure a project in a language other than English"
breadcrumb: []
source_path: "configuration/configproject.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configure a project in a language other than English

For translated versions of Costing Standard and Planning, the configuration of translated
versions is mostly the same as for English versions, except that the data appears in the whatever
language is supplied from the source data. However, some columns require English in order to
appropriately display content.

Applies to: Costing Standard and IT Financial Management on TBM Studio 12.8.2 and later, using
Template v107 and later

**Parent topic:** [Costing Standard](../home.html)

## Configuring non-English column names

The following information lists the column names that need to remain in English during
configuration. Check this list regularly as additional products are translated by
Apptio.

### Procedure

1. Either build your own drivers or edit the existing drivers to support the language you want.
2. Configure your allocations using precise columns in data relationships rather than using key columns (this is also true for English-language projects).
3. Ensure that project settings for paper size and locale are appropriately set for the language you want.
4. The sorting locale is maintained separately from the currency locale. Choose a sorting locale that best matches the language of the user or leave the locale as English if the target language doesn't need special sorting.
5. Retain the following columns in English, regardless of the language of the user:

   For ITP:

   - Cost Source Master Data
   - Expense Type
   - Plan Type
   - Labor Master Data
   - Is Internal

   For CT:

   - None.
