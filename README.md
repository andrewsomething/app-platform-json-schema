# app-platform-json-schema

Tiny utility to generate a JSON Schema for the DigitalOcean App Spec from OpenAPI.

```
$ node index.js --help
Usage: app-platform-json-schema [options]

Options:
  --spec       Location of the bundled DigitalOcean OpenAPI spec; path or URL (Default: https://api-engineering.nyc3.digitaloceanspaces.com/spec-ci/DigitalOcean-public.v2.yaml)
  --optput     Path for output location (Default: app_spec.json)
```

The outputted JSON Schema is suitable for use with the [Red Hat VS Code YAML plugin](https://github.com/redhat-developer/vscode-yaml#associating-a-schema-to-a-glob-pattern-via-yamlschemas)
to provide validation and auto-completion when editing an [App Spec for DigitalOcean's App Platform](https://docs.digitalocean.com/products/app-platform/reference/app-spec/).

With the YAML plugin installed, you can associate the schema with `app.yaml` and `app.yml` files by adding the following to your VS Code [user and workspace settings](https://code.visualstudio.com/docs/getstarted/settings#_creating-user-and-workspace-settings):

```json
    "yaml.schemas": {
      "https://raw.githubusercontent.com/andrewsomething/app-platform-json-schema/main/app_spec.json": ["app.yaml", "app.yml"],
    },
```

You may also associate the schema with individual files by adding the following line to each file:

```yaml
# yaml-language-server: $schema=https://raw.githubusercontent.com/andrewsomething/app-platform-json-schema/main/app_spec.json
```
