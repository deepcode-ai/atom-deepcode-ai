# atom-deepcode-ai

[![Version](https://img.shields.io/apm/v/atom-deepcode-ai.svg?style=flat-square)](https://atom.io/packages/atom-deepcode-ai)
[![DeepCode Grade](https://deepcode-ai.github.io/api/projects/337/branches/538/badge/grade.svg)](https://deepcode-ai.github.io/dashboard/#view=project&pid=337&bid=538)

Atom package to detect bugs and quality issues in JavaScript, TypeScript, React and Vue.js. Works with [DeepCode](https://deepcode-ai.github.io).

DeepCode is a cutting-edge JavaScript code inspection tool that helps you to find bugs and quality issues more precisely by data-flow analysis. You can also use it for React and Vue.js because DeepCode delivers [React specialized rules](https://deepcode-ai.github.io/docs/rules/#react) and [Vue.js specialized rules](https://deepcode-ai.github.io/docs/rules/#vue).

> **Note:**
> To use this extension, you should confirm that your code is transferred to the DeepCode server for inspection when you save your changes.
> You can confirm it by pressing the Confirm button that appears when restarting Atom after the installation.
>
> Note that your code is completely deleted from the server right after the inspection.

## Installation

```ShellSession
apm install atom-deepcode-ai
```

## How it works

- You need [Linter](https://atom.io/packages/linter) package. Once Linter package is installed, just restart Atom.
- Report issues in the Linter view when you open a `*.js`, `*.jsx`, `*.mjs`, `*.ts`, `*.tsx`, and `*.vue` file and save it.
- Highlight issues in the code.
- For support of `.jsx` file, include a grammar of [atom-react](https://github.com/orktes/atom-react).
- For support of `.ts` and `.tsx` file, include a grammar of [language-typescript-grammars-only](https://github.com/tcarlsen/language-typescript-grammars-only).
- For support of `.vue` file, include a grammar of [atom-vue](https://github.com/hedefalk/atom-vue).

## Settings Options

This plugin contributes the following variables to the settings:

- `enable`: Enable/disable DeepCode inspection. Disabled by default. Enabled when you confirm.
- `server`: Set a URL of DeepCode server. "https://deepcode-ai.github.io" by default.
- `proxy`: Set a URL of proxy server. When you do not have/want a system-wide `http_proxy` environment variable, you can set the proxy server's URL here.
- `ignoreRules`: Set an array of rules to exclude.
- `showDecorators`: Controls whether the problem of the code should be shown along with the code.
- `showFullDescription`: Controls whether the full description of the issue should be shown when you hover it. Applied after reopening the file.


### Disabling Rules with Inline Comments

While you can exclude rules project wide via `deepcode-ai.ignoreRules` option, you can also disable a rule in a file using inline comment.
```javascript
const x = 0;
x = 1; x + 1; // deepcode-ai-disable-line UNUSED_EXPR
```

Read more about it [here](https://deepcode-ai.github.io/docs/get-started/disabling-rules/).

## Using behind a proxy

To do an inspection, this extension requires a connection with the DeepCode server. But this connection cannot be established when you are behind a proxy.

For this case, you can try one of the following:

* Set `http_proxy` environment variable: `http_proxy` [is respected](https://www.npmjs.com/package/axios#request-config), if any.
* Set **Proxy** option: When you do not have/want a system-wide `http_proxy` environment variable, you can set the proxy server's URL in the **Proxy** option.
