# Library Example Buildkite Plugin

An example [Buildkite Plugin](https://buildkite.com/docs/agent/v3/plugins) for adding your own library of commands to expose to build jobs.

It works by providing [an `environment` hook](hooks/environment) which updates `$PATH` to include the `bin` directory containing the additional commands to expose to build jobs.

You can use this pattern to create your own plugin and consolidate and version your own commands and scripts between build pipelines.

This plugin pattern is generally less preferred than creating smaller, more declarative plugins with their own YAML based API. But for some situations, this library plugin pattern can be handy.

## Usage

```yml
steps:
  # Run the included simple-command script that echos
  - command: simple-command
    plugins:
      library-example#v1.0.0: ~

  # Run the included hello-world script that runs a Docker container
  - command: hello-world
    plugins:
      library-example#v1.0.0: ~

  # Run the included hello-world from inside a bash process, showing that you can run the library of commands within your own scripts and processes (e.g. `my-script.sh`)
  - command: bash -c 'hello-world'
    plugins:
      library-example#v1.0.0: ~
```

## License

MIT (see [LICENSE](LICENSE))
