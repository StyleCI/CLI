# StyleCI CLI Tool

![StyleCI Banner](https://user-images.githubusercontent.com/2829600/72653462-e6dd0e80-3982-11ea-8d12-9cc1e5057af1.jpg)

## Installation

The StyleCI CLI Tool requires [PHP](https://php.net) 7.2.5 or higher, and can be installed either by directly downloading the phar, or using [Composer](https://getcomposer.org/).

### Download the Phar

Global installation:

```bash
$ curl -SsLo styleci.phar https://github.com/StyleCI/CLI/releases/download/v1.3.2/styleci.phar \
    && chmod +x styleci.phar && sudo mv styleci.phar /usr/local/bin/styleci
```

### Require using Composer

Local installation:

```bash
$ composer require styleci/cli:^1.3 --dev
```

Global installation:

```bash
$ composer global require styleci/cli:^1.3
```

## First Time Setup

When using the tool for the first time, you may want to enter your StyleCI API keys. You can do this with the `styleci config` command, which will store your keys in `~/.styleci/config.json`, just like how Composer store keys.

#### StyleCI for GitHub:

```
styleci config auth.github YOUR-API-KEY-GOES-HERE
```

> Your API key is available at https://github.styleci.io/profile.

#### StyleCI for GitLab:

```
styleci config auth.gitlab YOUR-API-KEY-GOES-HERE
```

> Your API key is available at https://gitlab.styleci.io/profile.

#### StyleCI for Bitbucket:

```
styleci config auth.bitbucket YOUR-API-KEY-GOES-HERE
```

> Your API key is available at https://bitbucket.styleci.io/profile.


## Usage

Now, you can analyze any local copy of a repo enabled in StyleCI, from the console! Simply run:

```bash
$ styleci
```

and StyleCI will analyze your current directory.

### Environment Variables

If you have chosen not use the first time setup config, or would like to temporarily override the stored keys, this can be done by setting environment variables.

#### StyleCI for GitHub:

```bash
$ STYLECI_GITHUB_API_KEY=YOUR-API-KEY-GOES-HERE styleci
```

#### StyleCI for GitLab:

```bash
$ STYLECI_GITLAB_API_KEY=YOUR-API-KEY-GOES-HERE styleci
```

#### StyleCI for Bitbucket:

```bash
$ STYLECI_BITBUCKET_API_KEY=YOUR-API-KEY-GOES-HERE styleci
```

### Advanced Usage

You can optionally pass a directory to analyze, otherwise, the current working directory will be used. Moreover, we support analyzing only the changed files, performing a "dry run" without touching your files, and more:

```
Usage:
  analyze [options] [--] [<directory>]

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

Note that `styleci` is shorthand for `styleci analyze`. This will matter if you want to analyze a directory with relevative path `config`, or any other command name. You will need to write `styleci analyze config` in order to use such a `<directory>` argument.

## License

This tool is licensed under [The Apache License 2.0](LICENSE).
