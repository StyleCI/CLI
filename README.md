# StyleCI CLI Tool

![StyleCI Banner](https://user-images.githubusercontent.com/2829600/72653462-e6dd0e80-3982-11ea-8d12-9cc1e5057af1.jpg)

## Installation

The StyleCI CLI Tool requires [PHP](https://php.net) 7.2.5 or higher, and can be installer either by using Composer, or directly downloading the phar.

### Require using Composer

Local installation:

```bash
$ composer require --dev styleci/cli:^0.5
```

Global installation:

```bash
$ composer global require styleci/cli:^0.5
```

### Download the Phar

Global installation:

```bash
$ curl -SsLo styleci.phar https://github.com/StyleCI/CLI/releases/download/v0.5.0/styleci.phar \
    && chmod +x styleci.phar && sudo mv styleci.phar /usr/local/bin/styleci
```

## Usage

Now, you can analyze any local copy of a repo enabled in StyleCI, from the console!

### StyleCI for GitHub

```bash
$ STYLECI_GITHUB_API_KEY=YOUR-API-KEY-GOES-HERE styleci
```

> Your API key is available at https://github.styleci.io/profile.

### StyleCI for GitLab

```bash
$ STYLECI_GITLAB_API_KEY=YOUR-API-KEY-GOES-HERE styleci
```

> Your API key is available at https://gitlab.styleci.io/profile.

### StyleCI for Bitbucket

```bash
$ STYLECI_BITBUCKET_API_KEY=YOUR-API-KEY-GOES-HERE styleci
```

> Your API key is available at https://bitbucket.styleci.io/profile.

### API Key Storage

You may want to set this environment variable more permanent in practice, such as by exporting it in your `~/.zprofile` file.

### Advanced Usage

You can optionally pass a directory to analyze, otherwise, the current working directory will be used. Moreover, we support analyzing only the changed files, performing a "dry run" without touching your files, and more:

```
Usage:
  styleci [options] [--] [<directory>]

Arguments:
  directory

Options:
  -c, --only-changed
  -d, --dry-run
  -g, --git-binary=GIT-BINARY
  -r, --remote-name=REMOTE-NAME
  -h, --help                     Display this help message
  -q, --quiet                    Do not output any message
  -V, --version                  Display this application version
      --ansi                     Force ANSI output
      --no-ansi                  Disable ANSI output
  -n, --no-interaction           Do not ask any interactive question
  -v|vv|vvv, --verbose           Increase the verbosity of messages
```

## License

This tool is licensed under [The Apache License 2.0](LICENSE).
