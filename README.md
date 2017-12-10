# Vscode intellisense issue

## Context

Many repositories are now monorepos, with a `packages` folder and n packages. To help import something from a package A in another package B, we want to make use of `jsconfig.json`'s `compilerOptions.paths`.

## Showcase

`packages/app1/test.js` imports both a local and a shared util. When trying to CMD+click to go to definition, it works on both. But when typing the import, Intellisense only works on the local util.

Also, `packages/shared/utils/sharedUtil2.js` imports a shared util (using `@org/shared` for consistence), and Intellisense doesn't work either.

## Notes

I tried both these options:

```
"@org/shared/*": ["../../shared/*"],
"org/*": ["../../shared/*"]
```

To showcase the problem doesn't seem to lie in the use of the characters `@` or `/`
