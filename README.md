# Template Extension Specification

- **Title:** Validate
- **Identifier:** <https://raw.githubusercontent.com/baloola/validate/refs/heads/main/json-schema/schema.json>
- **Field Name Prefix:** -
- **Scope:** Item, Collection
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Proposal
- **Owner**: @your-gh-handles @person2

This document explains the Validate Extension to the [SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) (STAC) specification.
This is the place to add a short introduction.

- Examples:
- [Collection example](examples/collection.json): Shows the basic usage of the extension in a STAC Collection
- [Item example](examples/item.json): Shows the basic usage of the extension in a STAC Item
- [JSON Schema](json-schema/schema.json)
- [Changelog](./CHANGELOG.md)

## Fields

The fields in the table below can be used in these parts of STAC documents:

- [x] Catalogs
- [x] Collections
- [x] Item Properties (incl. Summaries in Collections)
- [] Assets (for both Collections and Items, incl. Item Asset Definitions in Collections)
- [ ] Links

| Field Name                     | Type                      | Description                                  |
| --------------------           | ------------------------- | -------------------------------------------- |
| validate:quality_measures      | string                    | Describe applied quality measures on data (standardised calibration, repeated samples or measurements, data capture, data entry validation, peer review of data, or representation with controlled vocabularies) |
| validate:workflow              | [Link Object](#link-object) | Describe the field...                        |
| template:another_one           | \[number]                 | Describe the field...                        |


### Link Object

This object describes a relationship with another entity.

| Field Name | Type   | Description |
| ---------- | ------ | ----------- |
| href       | string | **REQUIRED.** The actual link in the format of an URL. Relative and absolute links are both allowed. |
| rel        | string | **REQUIRED.** Relationship between the current document and the linked document. |
| type       | string | Media type of the referenced entity. |
| title      | string | A human readable title to be used in rendered displays of the link. |


## Contributing

All contributions are subject to the
[STAC Specification Code of Conduct](https://github.com/radiantearth/stac-spec/blob/master/CODE_OF_CONDUCT.md).
For contributions, please follow the
[STAC specification contributing guide](https://github.com/radiantearth/stac-spec/blob/master/CONTRIBUTING.md) Instructions
for running tests are copied here for convenience.

### Running tests

The same checks that run as checks on PR's are part of the repository and can be run locally to verify that changes are valid.
To run tests locally, you'll need `npm`, which is a standard part of any [node.js installation](https://nodejs.org/en/download/).

First you'll need to install everything with npm once. Just navigate to the root of this repository and on
your command line run:
```bash
npm install
```

Then to check markdown formatting and test the examples against the JSON schema, you can run:
```bash
npm test
```

This will spit out the same texts that you see online, and you can then go and fix your markdown or examples.

If the tests reveal formatting problems with the examples, you can fix them with:
```bash
npm run format-examples
```
