---
title: Getting Started
layout:  null
tab: true
order: 1
tags: deepsecrets
---

# Getting Started
## Installation

From Github via pip

`$ pip install git+https://github.com/ntoskernel/deepsecrets.git`

From PyPi

`$ pip install deepsecrets`

## Scanning

The easiest way:

`$ deepsecrets --target-dir /path/to/your/code --outfile report.json`

This will run a scan against `/path/to/your/code` using the default configuration:
- Regex checks by a small built-in ruleset
- Semantic checks (variable detection, entropy checks)

Report will be saved to `report.json`

### Fine-tuning
Run `deepsecrets --help` for details.

Basically, you can (and should) use your own regex-ruleset by specifying `--regex-rules`. Building rulesets is described in the next section.

Paths to be excluded from scanning can be set via `--excluded-paths`. The default set of excluded paths is here: `/deepsecrets/rules/excluded_paths.json`, you can write your own following the format.

## Building rulesets

### Regex

The built-in ruleset for regex checks is located in `/deepsecrets/rules/regexes.json`. You're free to follow the format and create a custom ruleset.

### HashedSecret

Example ruleset for hashed checks is located in `/tests/fixtures/hashed_secrets.json`. You're free to follow the format and create a custom ruleset.


