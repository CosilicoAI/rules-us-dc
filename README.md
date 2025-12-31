# DC Rules (Akoma Ntoso XML)

District of Columbia statutes and regulations in Akoma Ntoso XML format for the Cosilico rules-as-code pipeline.

## Directory Structure

```
rules-us-dc/
├── statutes/      # DC Code (synced from dccouncil/law-xml-codified)
└── regulations/   # DC Municipal Regulations (DCMR)
```

## Data Sources

### Statutes

DC Code statutes are sourced from the [DC Council's law-xml-codified repository](https://github.com/dccouncil/law-xml-codified), which provides the official DC Code in Akoma Ntoso XML format.

We copy rather than fork this repository to:
1. Control the directory structure for our pipeline
2. Add regulations alongside statutes
3. Maintain a clean separation of concerns

### Regulations

DC Municipal Regulations (DCMR) are sourced from the [DC Register](https://www.dcregs.dc.gov/).

## Usage

This repository feeds into the Cosilico rules-as-code encoding pipeline. The Akoma Ntoso XML format provides structured legal text with semantic markup for:

- Cross-references between sections
- Definitions and terms
- Effective dates and temporal versioning
- Legislative history

## Sync Process

Statutes are periodically synced from the upstream DC Council repository. To manually sync:

```bash
# Clone the source
git clone https://github.com/dccouncil/law-xml-codified.git /tmp/law-xml-codified

# Copy relevant files to statutes/
cp -r /tmp/law-xml-codified/dc/council/code/* statutes/
```

## License

The DC Code and DC Municipal Regulations are public domain as works of the District of Columbia government.
