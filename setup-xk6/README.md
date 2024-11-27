## k6-extension-actions/setup-xk6

Setup [xk6](https://github.com/grafana/xk6) to build k6 with extensions.

The latest version of `xk6` will be installed and placed in the search path. Installation is done from the GitHub releases page using the [eget](https://github.com/zyedidia/eget) tool. By default, the latest version is installed, but this can be overridden using the `xk6-version` input parameter.

**Usage**

```yaml
      - name: Setup xk6
        uses: grafana/k6-extension-actions/setup-xk6@v0.1.0

      - name: Build
        run: |
          xk6 build --with github.com/grafana/xk6-sql=.
```