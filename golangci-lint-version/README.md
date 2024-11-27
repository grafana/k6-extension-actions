## k6-extension-actions/golangci-lint-version

Composite GitHub action to provide the version of [golangci-lint](https://github.com/golangci/golangci-lint) to use.

The `golangci-lint` version is parsed from the first comment line of `.golangci.yml` file. The first line must contain the version number after the comment character ('#') and a space character. If the `.golangci.yml` file does not exist or its first line does not contain a version number, the `.golangci.yml` file on the default branch of the `grafana/k6` repository will be downloaded and used to determine the version.

The version number is returned in the `version` output variable.

**Usage**

```yaml
      - name: Retrieve golangci-lint version
        uses: grafana/k6-extension-actions/golangci-lint-version@v0.1.0
        id: golangci-lint-version

      - name: Run golangci-lint
        uses: golangci/golangci-lint-action@v6
        with:
          version: ${{ steps.golangci-lint-version.outputs.version }}
          only-new-issues: true
```