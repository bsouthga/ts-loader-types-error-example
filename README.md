# ts-loader typings issue

Importing a npm TS module with bundled typings, when the entry is a JS file results in the TS module's typings not being recognized.

Run `npm test` to see the issue, which should be something like:

```shell
➜  ts-loader-error git:(master) npm test

> @ test ~/projects/ts-loader-error
> tsc && echo 'works!' && webpack

works!
ts-loader: Using typescript@2.4.1 and ~/projects/ts-loader-error/tsconfig.json
Hash: 836c8ecb865d0c8010fe
Version: webpack 3.3.0
Time: 859ms
    Asset     Size  Chunks             Chunk Names
bundle.js  42.4 kB       0  [emitted]  main
   [1] ./src/entry.js 20 bytes {0} [built]
   [2] ./src/imported.ts 64 bytes {0} [built] [1 error]
    + 3 hidden modules

ERROR in ./src/imported.ts
(1,10): error TS2305: Module '"~/projects/ts-loader-error/node_modules/event-rank/dist/src/index"' hasno exported member 'EventRank'.
➜  ts-loader-error git:(master)
```