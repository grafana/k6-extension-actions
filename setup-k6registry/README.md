## k6-extension-actions/setup-k6registry

Setup [k6registry](https://github.com/grafana/k6registry) to maintain the extension registry.

The latest version of `k6registry` will be installed and placed in the search path. Installation is done from the GitHub releases page using the [eget](https://github.com/zyedidia/eget) tool. By default, the latest version is installed, but this can be overridden using the `k6registry-version` input parameter.

**Usage**

```yaml
      - name: Setup k6registry
        uses: grafana/k6-extension-actions/setup-k6registry@v0.1.0

      - name: Run k6registry
        id: k6registry
        env:
          GITHUB_TOKEN: ${{github.token}}
        run: >
          k6registry -v
            --lint
            --out registry.json
            registry.yaml
```