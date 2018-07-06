# Example Library Buildkite Plugin

An example [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) that exposes your own library of scripts and commands to build jobs.

It works by providing [an `environment` hook](hooks/environment) which updates `$PATH` to include the `bin` directory containing the additional commands you want to expose to build jobs.

```yml
steps:
  # Example of a simple command that echos
  - command: my-simple-command
    plugins:
      example-library#v1.0.0: ~
  # Example of a command that runs a Docker container
  - command: hello-world
    plugins:
      example-library#v1.0.0: ~
  # Example that you can run the library of commands within your own scripts and processes
  - command: bash -c 'hello-world'
    plugins:
      example-library#v1.0.0: ~
```

## License

MIT (see [LICENSE](LICENSE))
