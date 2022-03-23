# epm-git-yarn-repro

Requirements:

- Yarn

Running `yarn install` with the configured Yarn 3.2.0 fails with the error:

```
➤ YN0001: │ Error: ember-promise-modals@https://github.com/simplabs/ember-promise-modals.git#commit=7a02bf670d0f8e84d4e50d0708624aa45bd61e5d: Assertion failed: Unsupported workflow
    at /Users/bitwolfe/code/epm-git-yarn-repro/.yarn/releases/yarn-3.2.0.cjs:426:1497
    at async ar.mktempPromise (/Users/bitwolfe/code/epm-git-yarn-repro/.yarn/releases/yarn-3.2.0.cjs:319:63472)
    at async /Users/bitwolfe/code/epm-git-yarn-repro/.yarn/releases/yarn-3.2.0.cjs:423:16
    at async ar.mktempPromise (/Users/bitwolfe/code/epm-git-yarn-repro/.yarn/releases/yarn-3.2.0.cjs:319:63472)
    at async /Users/bitwolfe/code/epm-git-yarn-repro/.yarn/releases/yarn-3.2.0.cjs:418:2513
```

For some reason it seems to get confused by the presence of a pnpm-lock file in the ember-promise-modals repo, almost like it sees and gives up before even trying to install from package.json.

Related issue in ember-promise-modals: https://github.com/simplabs/ember-promise-modals/issues/562
