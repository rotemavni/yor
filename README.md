# Yor
[![Maintained by Bridgecrew.io](https://img.shields.io/badge/maintained%20by-bridgecrew.io-blueviolet)](https://bridgecrew.io/?utm_source=github&utm_medium=organic_oss&utm_campaign=yor)
[![build status](https://github.com/bridgecrewio/yor/workflows/build/badge.svg)](https://github.com/bridgecrewio/yor/actions?query=workflow%3Abuild)
[![security status](https://github.com/bridgecrewio/yor/workflows/security/badge.svg)](https://github.com/bridgecrewio/yor/actions?query=event%3Apush+branch%3Amaster+workflow%3Asecurity) 
[![code_coverage](https://raw.githubusercontent.com/bridgecrewio/yor/master/coverage.svg?sanitize=true)](https://github.com/bridgecrewio/yor/actions?query=workflow%3Acoverage) 
[![Go Report Card](https://goreportcard.com/badge/github.com/bridgecrewio/yor)](https://goreportcard.com/report/github.com/bridgecrewio/yor)
[![Terraform Version](https://img.shields.io/badge/tf-%3E%3D0.12.0-blue.svg)](#)
[![slack-community](https://slack.bridgecrew.io/badge.svg)](https://slack.bridgecrew.io/?utm_source=github&utm_medium=organic_oss&utm_campaign=yor)



Automated IaC tagging for managing cloud resources.

Yor is a tagging automation utility for infrastructure-as-code. It uses Git-Blame data to tag resource blocks managed in IaC, with CMDB-like information such as repo, commit, author, etc.

## Supported tags

```
yor_trace = "842fa55e-c0f8-4f79-a56d-a046a24d8e08"
git_org = "bridgecrewio"
git_repo = "terragoat"
git_file = "README.md" # this is the path from the repo root dir...
git_commit = "47accf06f13b503f3bab06fed7860e72f7523cac" # This is the latest commit for this resource
git_last_modified_At = "2020-03-28 21:42:46 +0000 UTC"
git_last_modified_by = "schosterbarak@gmail.com"
git_modifiers = "schosterbarak/baraks" # These are extracted from the emails, everything before the @ sign. Can be done for modified_by tag as well
```

## **Table of contents**

- [Getting Started](#getting-started)
- [Disclaimer](#disclaimer)
- [Support](#support)

## Getting Started

### Installation

On MacOS

```sh
brew install yor
```

### Usage

* Tag an entire directory

```sh
yor --directory terraform/
```

### Skipping tags 

Using command line flags you can specify to run only named tags (allow list) or run all tags except 
those listed (deny list).

```sh
yor -d. --tag yor_trace
## Run only yor_trace

yor -d. --skip-tag yor_trace
## Run all but yor_trace

yor -d. --skip-tag git*
## Run all tags except tags with specified patterns

yor -d. --skip-tag
```

## Contributing

Contribution is welcomed!


## Disclaimer

`yor` does not save, publish or share with anyone any identifiable customer information.  

## Support

If you need direct support you can contact us at info@bridgecrew.io.
