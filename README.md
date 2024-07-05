Long Branch Church website ![Deploy Huge site to Pages](https://github.com/f3peakcity/f3peakcity.github.io/actions/workflows/hugo.yml/badge.svg?branch=main)

The Long Branch Church website site is built using Hugo and a fork of the [Beautiful Hugo theme](https://github.com/f3peakcity/beautifulhugo).

The site is published using GitHub pages, available at the following URLs:

- Production: [https://www.longbranchchurch.org/](https://www.longbranchchurch.org/)

## Contributors

People with admin rights:

- Brian Pugsley
- 
## Quick start

1. Clone the repo.
2. [Install Hugo](https://gohugo.io/installation/) version 0.119.0.
3. Navigate into the repo and run build the site locally.
   ```
   hugo server -D
   ```
4. Open [https://localhost:1313](https://localhost:1313) in your browser. The site will automatically refresh as you save changes to the locally cloned files.

## Local changes to the theme

If you want to make styling changes such as CSS to the beautifulhugo forked theme, you have a couple options to test local changes:

- In the `config.toml` file, [add a replace section](https://gohugo.io/hugo-modules/use-modules/#make-and-test-changes-in-a-module) to point to your local clone of the forked repo. Then make your changes in that repo and refresh your Hugo server.
- Use `hugo mod vendor` to download a [local `_vendor` directory](https://gohugo.io/hugo-modules/use-modules/#vendor-your-modules) in this `f3peakcity.github.io` project. Then make your changes in that `_vendor` directory and refresh your Hugo server.

## Updating the theme

The [forked Beautiful Hugo theme](https://github.com/f3peakcity/beautifulhugo) is added as a [Hugo module](https://gohugo.io/hugo-modules/). The general process to update the theme is as follows.

1. Make your theme changes in the [forked repo](https://github.com/f3peakcity/beautifulhugo).
2. [Create a new release](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository) for the theme changes. Naming convention is like `v0.0.1`.
3. Navigate to your clone of this repo and run `hugo mod get github.com/f3peakcity/beautifulhugo`.
4. Commit and push your changes.
