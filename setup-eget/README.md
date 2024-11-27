## k6-extension-actions/setup-eget

Setup [eget](https://github.com/zyedidia/eget) tool for installing GitHub releases.

The eget tool will be installed in the `.eget` folder within the workspace. The eget configuration will be created in the same folder as `.eget.toml`. The releases to be downloaded will also be placed in the same directory.

The `EGET_CONFIG` environment variable will be set and exported, it will contain the full path to the `.eget.toml` file. The `PATH` environment variable will include the `.eget` folder, so the installed tools will be automatically available on the path.

**Usage**

```yaml
      - name: Setup eget
        uses: grafana/k6-extension-actions/setup-eget@v0.1.0

      - name: Install gotestsum
        run: |
          eget gotestyourself/gotestsum
          gotestsum --version
```
