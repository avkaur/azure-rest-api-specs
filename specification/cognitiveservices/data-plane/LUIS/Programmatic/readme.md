# Cognitive Services LUIS SDKs

> see https://aka.ms/autorest

Configuration for generating LUIS Programmatic SDK.

``` yaml
tag: programmatic_2_0
add-credentials: true
openapi-type: data-plane
```

The current release for the Programmatic Endpoint is `programmatic_2_0`.

# Releases

## Programmatic 2.0
These settings apply only when `--tag=programmatic_2_0` is specified on the command line.

``` yaml $(tag) == 'programmatic_2_0'
input-file: v2.0/LUIS-Programmatic.json
```

Deprecated Pattern's Operations

``` yaml $(tag) == 'programmatic_2_0'
directive:
  - reason: Deprecated
    remove-operation: Features_GetApplicationVersionPatternFeatures
  - reason: Deprecated
    remove-operation: Features_CreatePatternFeature
  - reason: Deprecated
    remove-operation: Features_GetPatternFeatureInfo
  - reason: Deprecated
    remove-operation: Features_UpdatePatternFeature
  - reason: Deprecated
    remove-operation: Features_DeletePatternFeature
```

AutoRest-Linter Suppressions

``` yaml
# Ignore autorest-linter issues that cannot be resolve without updates to the API implementation
directive:
  - suppress: DeleteMustNotHaveRequestBody
    reason: Body is used to specify entity to delete
  - suppress: DefinitionsPropertiesNamesCamelCase
    reason: Changing casing will break existing clients/consumers
```

### Programmatic 2.0 - CSharp Settings
These settings apply only when `--csharp` is specified on the command line.
``` yaml $(csharp)
csharp:
  override-client-name: LuisProgrammaticAPI
  sync-methods: None
  license-header: MICROSOFT_MIT_NO_VERSION
  azure-arm: false
  namespace: Microsoft.Azure.CognitiveServices.Language.LUIS.Programmatic
  output-folder: $(csharp-sdks-folder)/CognitiveServices/dataPlane/Language/LUIS-Programmatic/Generated
  clear-output-folder: true
```

## Go

These settings apply only when `--go` is specified on the command line.

``` yaml $(go)
go:
  license-header: MICROSOFT_APACHE_NO_VERSION
  namespace: programmatic
  clear-output-folder: true
```

### Tag: programmatic_2_0 and go

These settings apply only when `--tag=programmatic_2_0 --go` is specified on the command line.
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`.

``` yaml $(tag) == 'programmatic_2_0' && $(go)
output-folder: $(go-sdk-folder)/services/cognitiveservices/luis/v2.0/programmatic
```