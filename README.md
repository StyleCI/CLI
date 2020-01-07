# StyleCI CLI Tool

## Installation

The StyleCI SDK requires [PHP](https://php.net) 7.2.5 or higher. Download `styleci.phar` from the [releases page](https://github.com/StyleCI/CLI/releases/latest), and put it in you faviouite location for bin files (alongside composer), removing the `.phar` from the filename.

## Usage

Now, you can analyze any local copy of a repo enabled in StyleCI, from the console!

```bash
$ export STYLECI_API_KEY=YOUR-API-KEY-GOES-HERE; styleci analyze
```

You can optionally pass a directory to analyze, otherwise, the current working directory will be used.

```
Usage:
  analyze [options] [--] [<directory>]

Arguments:
  directory                    

Options:
  -c, --only-changed           
  -d, --dry-run                
  -g, --git-binary=GIT-BINARY  
  -h, --help                   Display this help message
  -q, --quiet                  Do not output any message
  -V, --version                Display this application version
      --ansi                   Force ANSI output
      --no-ansi                Disable ANSI output
  -n, --no-interaction         Do not ask any interactive question
  -v|vv|vvv, --verbose         Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug
```
