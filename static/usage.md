# Usage

## Format Validation

External tools can be used to validate JSON documents against the CDM schema.

For example, to validate using [ajv-cli]( https://github.com/ajv-validator/ajv-cli) with the CDM schema in [cdmentities.json](../schema/cdmentities.json):

`ajv --verbose -c ajv-formats --spec=draft7 validate -s cdmentities.json -d your/cdm/document.json`

Flag explanations:

- `--verbose`: Provides detailed validation output
- `-c ajv-formats`: Loads the ajv-formats plugin for format validation
- `--spec=draft7`: Uses JSON Schema Draft 7 specification
- `-s`: Specifies the schema file (cdmentities.json)
- `-d`: Specifies the data/document file to validate

## Code completion in IDEs

The schema file can be used in IDEs that support code completion. For example, in Visual Studio Code, add the following to your JSON settings (`settings.json`) to associate the CDM schema with your JSON files:

```json
{
  "json.schemas": [
    {
      "fileMatch": ["cdm.json"],
      "url": "https://raw.githubusercontent.com/SAP/common-data-model/refs/heads/main/schema/cdmentities.json"
    }
  ]
}
```

Note: Adjust the `fileMatch` pattern to match your CDM document filenames (e.g., `["**/cdm/*.json"]` for all JSON files in a cdm folder).
