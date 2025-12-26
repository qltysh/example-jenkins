# Qlty Ruby Coverage Example

[Qlty](https://qlty.sh) is a Code Health Platform with support for code coverage.

This repository is an example using Qlty to track code coverage on a Jenkins server.

This repository uses [Rspec](https://rspec.info/) for testing and [simplecov](https://github.com/simplecov-ruby/simplecov) to generate test coverage.

## Requirements

- Ruby 2.7 or above
- Test run with [bundle exec rspec](https://rspec.info/)
- An account on Qlty (free for open source)
- `QLTY_COVERAGE_TOKEN` is set as an environment variable

## Set up

See [`Jenkinsfile`](./Jenkinsfile) in this repository for a basic configuration.

## Documentation

- [Ruby Code Coverage Setup](https://docs.qlty.sh/coverage/generating-data#ruby-with-simplecov)
- [Alternative supported CI providers](https://docs.qlty.sh/coverage/ci)

## Help and feedback

Join our [Discord](https://qlty.sh/discord) for help and feedback.

## License

[MIT License](./LICENSE.md)