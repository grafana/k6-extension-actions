## k6-extension-actions/k6-versions-to-test

Composite GitHub action to provide the list of k6 versions to test with extensions.

The k6 versions are retrieved from the k6 extension registry. The latest version is selected from the k6 versions and the latest patch version from the previous minor version.

The version number list is returned in the `versions` output variable as a JSON array of strings.

**Usage**

```yaml
jobs:

  configure:
    runs-on: ubuntu-latest
    outputs:
      k6-versions: ${{steps.k6-versions.outputs.versions}}
    steps:
      - name: Retrieve k6 versions to test
        id: k6-versions
        uses: grafana/k6-extension-actions/k6-versions-to-test@v0.1.0

  build:
    needs:
      - configure
    strategy:
      fail-fast: false
      matrix:
        k6-version: ${{ fromJSON(needs.configure.outputs.k6-versions) }}
        go-version: ["1.22.x", "1.21.x"]
        platform: ["ubuntu-latest", "windows-latest", "macos-latest"]
    runs-on: ${{ matrix.platform }}
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup Go ${{ matrix.go-version }}
        uses: actions/setup-go@v5
        with:
          go-version: ${{ matrix.go-version }}

      - name: Setup eget
        uses: grafana/k6-extension-actions/setup-eget@v0.1.0
      
      - name: Setup xk6
        uses: grafana/k6-extension-actions/setup-xk6@v0.1.0

      - name: Build k6
        run: |
          xk6 build ${{ matrix.k6-version }} --output ./k6 --with github.com/${{github.repository}}="."

      - name: Run k6 version
        run: ./k6 version
```