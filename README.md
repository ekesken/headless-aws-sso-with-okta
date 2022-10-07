## linksquares-headless-sso
Runs [aws sso login]() headlessly when using the `--no-browser` option.

[![Go Reference](https://pkg.go.dev/badge/github.com/mziyabo/headless-sso.svg)](https://pkg.go.dev/github.com/mziyabo/headless-sso) [![Go Report Card](https://goreportcard.com/badge/github.com/mziyabo/headless-sso)](https://goreportcard.com/report/github.com/mziyabo/headless-sso) 

### Background

We want to avoid leaving the terminal and opening yet another tab and having to click Next next next...

### Install

To download the latest release, run:
> For ARM systems, please change ARCH to `arm64`

``` sh
 curl --silent --location https://github.com/mziyabo/headless-sso/releases/latest/download/headless-sso_0.2.0_$(uname -s)_x86_64.tar.gz | tar xz -C /tmp/
 sudo mv /tmp/headless-sso /usr/local/bin
```

Alternatively:

``` sh
go install github.com/mziyabo/headless-sso@latest
```

**Windows**: Download latest Windows binary from the [Releases Page](https://github.com/mziyabo/headless-sso/releases) and unzip to location in PATH

#### Dependancies:

This tool requires you to have installed and configured Dashlane's official CLI tool. You can find installation instructions here: [Dashlane CLI](https://github.com/Dashlane/dashlane-cli/tree/master/src)
### Usage:

``` bash
aws sso login  --profile login --no-browser | headless-sso
```


**Note:** `headless-sso` gets the AWS user credentials from a `.netrc` file with the following format:
 > machine name has to be `headless-sso`

```
machine headless-sso
login <username>
password <something-secret>
```
**Example:**

![headless-sso demo](./docs/demo.gif)

### Limitations:
- Only works with hardware MFA. This means the case were MFA isn't used or is done by inputting the MFA token is presently unhandled.

### Release Notes:
Working but still WiP, contributions welcome.

### License:
Apache-2.0