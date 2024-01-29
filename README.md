# Sec Tools Buildkite Plugin

A [Buildkite Plugin](https://buildkite.com/docs/agent/v3/plugins) for opensource security scanners.

## Examples

```yml
steps:
  - command: gitleaks
    plugins:
      - sjames-au/sectools#v0.0.1: ~
```

## License

MIT (see [LICENSE](LICENSE))
