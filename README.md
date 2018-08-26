# Jupyter Renderers

This is a [monorepo](https://github.com/lerna/lerna#what-does-a-lerna-repo-look-like) that consists of generic renderers for common file types and mime types as well as renderer extensions for [JupyterLab](https://github.com/jupyterlab/jupyterlab).

## Packages

| Name                                        | Mime types | File extensions |
| ------------------------------------------- | ---------- | --------------- |
| [my-mathjax2-ext](packages/my-mathjax2-ext) | N/A        | N/A             |
| [my-mathjax3-ext](packages/my-mathjax3-ext) | N/A        | N/A             |

Please note my-mathjax3-ext is a work-in-progress. Macros are not currently supported unless a custom package of MathJax is built.

## Install

### My Mathjax 2 Extension

First, disable the default MathJax 2 Extension
`jupyter labextension disable @jupyterlab/mathjax2-extension`

Install My Mathjax 2 Extension (my-mathjax2-ext)
`jupyter labextension install sparkboom/my-mathjax2-ext`

### My Mathjax 3 Extension

- my-mathjax3-ext: `jupyter labextension install sparkboom/my-mathjax3-ext`

## Requirements

- Node.js >= 4 (see [Installing Node.js and jlpm](https://github.com/jupyterlab/jupyterlab/blob/master/CONTRIBUTING.md#installing-nodejs-and-jlpm) in the JupyterLab docs)

### Install

The `jlpm` command is JupyterLab's pinned version of
[yarn](https://yarnpkg.com/) that is installed with JupyterLab. You may use
`yarn` or `npm` in lieu of `jlpm` below.

```bash
git clone https://github.com/sparkboom/jupyterlab-extensions.git
cd jupyterlab-extensions
jlpm
jlpm build
```

### Link extensions with JupyterLab

Link my-mathjax2-ext:

```bash
jupyter labextension link packages/my-mathjax2-ext
```

Link my-mathjax3-ext:

```bash
jupyter labextension link packages/my-mathjax3-ext
```

Link all extensions in `packages`:

```bash
jlpm run link
```

### Rebuilding extensions

After making changes to the source packages, the packages must be rebuilt:

```bash
# Rebuild the source
jlpm build

# Rebuild the JupyterLab staging directory
jupyter lab build
```

You may also watch the `jupyterlab-extensions` directory for changes and automatically rebuild:

```bash
# In one terminal tab, watch the jupyterlab-extensions directory
jlpm watch

# In another terminal tab, run jupyterlab with the watch flag
jupyter lab --watch
```

### Publishing packages

```bash
jlpm publish
# If publishing a package for the first time
npm access public sparkboom/<extension name>
```
