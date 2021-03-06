# Bash Cache Buildkite Plugin

A caching plugin that can be invoked from your build script

## Example

For a directory structure that looks like:

```
my-project/
├── node_modules/
├── package.json
├── package-lock.json

```

Add the following to your `pipeline.yml`:


```yml
steps:
  - command: |
      # To persist the cache
      save_cache node_modules/ $(hash_file package-lock.json)

      # To restore the cache, if present
      restore_cache $(hash_file package-lock.json)

    plugins:
      - automattic/bash-cache#v1.0.0
```

## Configuration

There are no configuration options for this plugin

## Developing

To run the linter and tests:

```shell
docker-compose run --rm lint
docker-compose run --rm tests
```

## Contributing

1. Fork the repo
2. Make the changes
3. Run the tests
4. Commit and push your changes
5. Send a pull request
