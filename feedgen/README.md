# feedgen

Since hugo has no support for podcast feeds, we're going manual. This tool reads the project config and content and uses a template to generate a valid podcast RSS feed. In doing so it overwrites whatever hugo generated as the RSS feed, since podcast feeds are also just normal RSS feeds.
It therefore makes sense to run this right after running hugo, ideally as a Makefile step.

## Notes

Posts are expected to not contain any straight HTML.

Necessary frontmatter values for posts are:

```yaml
---
title:
slug:
author:
date: # y-MM-dd
audio:
length: # bytecount
duration: # HH:mm:ss
blurb:
---
```

## Usage

```
OVERVIEW: Generate a podcast feed for a hugo page.

USAGE: feedgen [--config-path <config-path>] [--template-path <template-path>] [--items-path <items-path>] [--output-path <output-path>]

OPTIONS:
  -c, --config-path <config-path>
                          Path to config.toml of hugo project, defaults to './config.toml'.
  -t, --template-path <template-path>
                          Path to directory containing feed stencil template , defaults to './resources/'.
  -i, --items-path <items-path>
                          Path to content markdown files, defaults to './content/post/'.
  -o, --output-path <output-path>
                          Path to write generated feed to, defaults to './docs/index.xml'.
  --version               Show the version.
  -h, --help              Show help information.
```
