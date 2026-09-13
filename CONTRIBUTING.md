# Contributing

Thanks for improving the Voltrus SDKs.

## Repository layout

```
sdk/typescript/   TypeScript client (published to npm as `voltrus`)
sdk/python/       Python client (published to PyPI as `voltrus`)
```

Both clients target the Voltrus v1 HTTP API (`/api/v1/...`) and are modeled on
the OpenAPI spec your server exposes at `/api/v1/openapi.json`.

## Development

TypeScript (Node 18+, npm):

```bash
cd sdk/typescript
npm install
npm run typecheck            # src
npm run typecheck:examples   # examples/ must stay type-clean
npm run build                # emits dist/
```

Python (3.9+):

```bash
cd sdk/python
pip install .
python -m unittest discover -s tests -v
```

## Ground rules

- Every PR keeps typechecks and tests green.
- Examples under `examples/` must run against a stock Voltrus server — no
  internal or staging endpoints.
- Keep credentials out of the repo; examples read `VOLTRUS_*` env vars.
- Behavior changes belong in both SDKs where the feature exists in both.

## Releases

Maintainers run `publish.sh` in each SDK directory (npm / twine). Versions of
both SDKs are kept in lockstep with the server release they are tested against.
