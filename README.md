# 🚨 cop (v.): to acquire without concern, esp. via illicit means; *finesse*

> im lazy af lol.
>
> --Bill Gates

# EXAMPLES

```console
$ cop "https://jsonip.com/"
Using curl...
{"ip":"123.123.123.123"}
```

# ABOUT

cop is an HTTP client agnostic file downloader. Given a URL, cop searches for well-known clients installed on your system and selects the first one it finds.

cop emits file contents to STDOUT by default. This makes it great for troubleshooting small, text file URLs. [Pipe or redirect](https://www.tldp.org/LDP/abs/html/io-redirection.html) the output as needed. Example:

```console
$ cop https://jsonip.com/ | jq .
Using wget...
{
  "ip": "123.123.123.123"
}
```

# WHY COP?

* Reduce vendor lock-in of curl vs. wget
* Run on more platforms, including macOS, Linux, UNIX, Git Bash, Cygwin, MSYS, MinGW, and Windows Subsystem for Linux.
* Build muscle memory across platforms
* Bootstrap software components
* Get $$$rich like Bill Gates

# REQUIREMENTS

* [sh](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/sh.html) (often automatically shimmed from ash, bash, ksh, zsh, etc.)

## Recommended

* [vast](https://github.com/mcandre/vast)
* [jq](https://stedolan.github.io/jq/)

# INSTALL

1. Copy cop.
2. Add ...`/bin` to `PATH`.

# LINT + TEST

```console
$ vast
```

# NOTES

* Most client-specific flags are dropped.
* Some clients lack (S)FTP((E)S) support.
* Some older clients like `ftp` may have difficulty processing `https://`... URLs.
* Some older clients like `lynx`, `links` may pad file contents. Such padding would yield different checksums.
* If you accidentally spill raw binary file contents onto the terminal, try `reset`.
