## k6-extension-actions/setup-k6lint

Setup [k6lint](https://github.com/grafana/k6lint) to check the compliance of extensions.

The latest version of `k6lint` will be installed and placed in the search path. Installation is done from the GitHub releases page using the [eget](https://github.com/zyedidia/eget) tool. By default, the latest version is installed, but this can be overridden using the `k6lint-version` input parameter.

**Usage**

```yaml
      - name: Checkout
        uses: actions/checkout@v4
        with:
          fetch-depth: 0

      - name: Setup k6lint
        uses: grafana/k6-extension-actions/setup-k6lint@v0.1.0

      - name: Run k6lint
        run: |
          k6lint --passing B
```
