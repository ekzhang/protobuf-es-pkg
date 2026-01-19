# protobuf-es-pkg

Code generation repository for Protobuf packages in JavaScript using [`@bufbuild/protobuf`](https://github.com/bufbuild/protobuf-es).

## Updating

1. Change `buf.gen.yaml` with the required configuration (new tag, etc.).
2. Run `pnpm i && pnpm build`.
3. Change version and `pnpm publish`.
