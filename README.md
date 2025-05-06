# k6-extension-actions

> [!WARNING]
> **Deprecated**. Use the reusable workflows from [xk6](https://github.com/grafana/xk6) or the [setup-xk6](https://github.com/grafana/setup-xk6) action.

Set of reusable composite GitHub actions to support k6 extension development.

The following composite actions can be found in the folders with the same name:

Name                                   | Summary
---------------------------------------|--------
[`setup-eget`](setup-eget)             | Setup [eget](https://github.com/zyedidia/eget) tool for installing GitHub releases
[`setup-k6lint`](setup-k6lint)         | Setup [k6lint](https://github.com/grafana/k6lint) to check the compliance of extensions.
[`setup-k6registry`](setup-k6registry) | Setup [k6registry](https://github.com/grafana/k6registry) to maintain the extension registry.
[`setup-xk6`](setup-xk6)               | Setup [xk6](https://github.com/grafana/xk6) to build k6 with extensions.
[`k6-versions-to-test`](k6-versions-to-test) | Provide the list of k6 versions to test with extensions.
[`golangci-lint-version`](golangci-lint-version) | Provide the version of [golangci-lint](https://github.com/golangci/golangci-lint) to use.
