# setup-openapi-generator-cli
Install `openapi-generator-cli` [OpenAPITools Generator](https://github.com/OpenAPITools/openapi-generator)

## Inputs

### `generator-tag`

The Docker tag of the openapitools/openapi-generator-cli image to use. See [the DockerHub repo](https://hub.docker.com/r/openapitools/openapi-generator-cli/tags) for available tags.

## Outputs

No outputs are returned. `openapi-generator-cli` should be added to the path.

## Example usage
```yaml
jobs:
  generate-angular-client:
    runs-on: ubuntu-latest
    name: Example
    steps:

      # Checkout your code
      - name: Checkout
        uses: actions/checkout@v2

      # Generate your OpenAPI document (if you don't write it manually)

      # Use the action to generate a client package
      # This uses the default path for the openapi document and thus assumes there is an openapi.json in the current workspace.
      - name: Generate Angular Client
        uses: ethan92429/setup-openapi-generator-cli@v1
      - run: openapi-generator-cli -g typescript-angular -c angular-generator-config.yml

      # Do something with the generated client (likely publishing it somewhere)
      - name: Do something with the client
        run: |
          cd typescript-angular-client
```
