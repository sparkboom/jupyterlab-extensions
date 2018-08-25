# Jupyter Renderers

This is a [monorepo](https://github.com/lerna/lerna#what-does-a-lerna-repo-look-like) that consists of generic renderers for common file types and mime types as well as renderer extensions for [JupyterLab](https://github.com/jupyterlab/jupyterlab).

## Packages

| Name                                              | Mime types | File extensions |
| ------------------------------------------------- | ---------- | --------------- |
| [mathjax3-extension](packages/mathjax3-extension) | N/A        | N/A             |

## Install

- mathjax3-extension: `jupyter labextension install sparkboom/my-mathjax3-ext`

## Requirements

- Node.js >= 4 (see [Installing Node.js and jlpm](https://github.com/jupyterlab/jupyterlab/blob/master/CONTRIBUTING.md#installing-nodejs-and-jlpm) in the JupyterLab docs)

### Install

The `jlpm` command is JupyterLab's pinned version of
[yarn](https://yarnpkg.com/) that is installed with JupyterLab. You may use
`yarn` or `npm` in lieu of `jlpm` below.

```bash
git clone https://github.com/sparkboom/my-mathjax3-ext.git
cd my-mathjax3-ext
jlpm
jlpm build
```

### Link extensions with JupyterLab

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

You may also watch the `my-mathjax3-ext` directory for changes and automatically rebuild:

```bash
# In one terminal tab, watch the my-mathjax3-ext directory
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
