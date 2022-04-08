# jest-esm-process-mutate-repro

Reproduction repository for [facebook/jest#12650](https://github.com/facebook/jest/issues/12650).

When running jest as ESM (with node `--experimental-vm-modules` flag) and importing (in this order) `node:process` and a
custom CJS module that adds properties to `node:process` module, jest-runtime crash with the following error

```
ReferenceError: Export 'xxx' is not defined in module` error.
```

### Reproduce

```shell
npm install
npm run test # test-import-process-before.cjs.spec.js cause the crash
```