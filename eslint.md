# ESLint

ESLint is super usefull package to check syntax in node projects, works well with vim so that vim can
perform a check every time a file is changed:

In order to use vim with local installation of eslint:

- [vim plugin](https://github.com/mtscout6/syntastic-local-eslint.vim)

To make it work

_____syntastyc__

- [Install Syntastic](https://github.com/vim-syntastic/syntastic)
- In vim conf:

```
    "==============================================================
    " jsx
    "==============================================================
    let g:jsx_ext_required=0
    let g:javascript_enable_domhtmlcss=1
    let g:syntastic_javascript_checkers = ['eslint']
```

__ale__

- [Install Ale](https://github.com/w0rp/ale)
- In vim conf:
```
    let g:ale_fixers = {'javascript': ['prettier', 'eslint'], 'scss': ['prettier'], 'python': ['yapf', 'isort']}

    let g:ale_javascript_prettier_use_local_config = 1
    let g:ale_linters = {
    \   'scss': ['sasslint'],
    \   'javascript': ['eslint'],
    \}
```

__Local eslint configuration__

- .eslintrc (example)

```
    {
      "parser": "babel-eslint",
      "extends": [
        "standard",
        "standard-react"
      ],
      "plugins": [
        "babel",
        "react",
        "promise"
      ],
      "env": {
        "browser" : false
      },
      "globals": {
        "$LOCALES"  : {},
        "__DEV__"      : false,
        "__TEST__"     : false,
        "__PROD__"     : false,
        "__STAGING__"  : false,
        "__COVERAGE__" : false
      },
      "rules": {
        "key-spacing"          : 0,
        "jsx-quotes"           : [2, "prefer-single"],
        "max-len"              : [2, 120, 2],
        "object-curly-spacing" : [2, "always"]
      }
    }
```

- .eslintignore (example)

```
    blueprints/**/files/**
    coverage/**
    node_modules/**
    dist/**
    src/index.html
```

- Install locally the following packages (for react/react native):

```
    "babel-eslint": "^7.2.3",
    "eslint": "^4.0.0",
    "eslint-config-standard": "^10.2.1",
    "eslint-config-standard-react": "^5.0.0",
    "eslint-plugin-babel": "^4.1.1",
    "eslint-plugin-import": "^2.5.0",
    "eslint-plugin-node": "^5.0.0",
    "eslint-plugin-promise": "^3.5.0",
    "eslint-plugin-react": "^7.1.0",
    "eslint-plugin-standard": "^3.0.1",
```
