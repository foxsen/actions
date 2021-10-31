# setup-tinytex-new

[![RStudio community](https://img.shields.io/badge/community-github--actions-blue?style=social&logo=rstudio&logoColor=75AADB)](https://community.rstudio.com/new-topic?category=Package%20development&tags=github-actions)

This action installs TinyTex for producing pdf by:

- Installing [TinyTex](https://yihui.org/tinytex/) via tinytex r package
- Setting up a cache using [actions/cache](https://github.com/actions/cache). TinyTex installation involves two major steps, the first one is downloading and installing the main framework package(tens of Mega bytes), the second one is installing required tex packages during pdf generation. We cached the final result and skip both steps if cache hit.

r-lib/actions/setup-renv does not used cache.

# Usage

Inputs available

- `cache-version` - default `1`. If you need to invalidate the existing cache pass any other number and a new cache will be used.

Basic:
```yaml
steps:
- uses: actions/checkout@master
- uses: foxsen/actions/setup-r@v1
- uses: foxsen/actions/setup-renv@renv-v2
  with:
    cache-version: 2
- uses: foxsen/actions/setup-tinytex-new@tinytex-v2
  with:
    cache-version: 1
```

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)

# Contributions

Contributions are welcome!
