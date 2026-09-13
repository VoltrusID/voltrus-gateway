# Voltrus SDKs
[![CI](https://github.com/VoltrusID/voltrus-gateway/actions/workflows/ci.yml/badge.svg)](https://github.com/VoltrusID/voltrus-gateway/actions/workflows/ci.yml)

Official client SDKs for the [Voltrus SCADA](https://voltrus.com) server.
Target: Voltrus v1 HTTP API, tested against server 0.47.x. See each SDK README for authentication, examples, and troubleshooting.

| Language | Package | Install |
|----------|---------|---------|
| TypeScript | [`voltrus` on npm](https://www.npmjs.com/package/voltrus) | `npm install voltrus` |
| Python | `voltrus` on PyPI | `pip install voltrus` |

## Quick start

```typescript
// TypeScript
import { VoltrusClient } from "voltrus";

const client = new VoltrusClient({
  basePath: "http://your-server:3000",
  apiKey: process.env.VOLTRUS_API_KEY,
});
const data = await client.data.getLiveData({ screenId: "overview" });
```

```python
# Python
from voltrus import VoltrusClient

client = VoltrusClient("http://your-server:3000", api_key="vt_...")
print(client.get_live_data(screen_id="overview"))
```

See the language-specific READMEs for the full API surface, authentication options
(API key, session login, OIDC bearer), and runnable examples:

## Documentation

The API reference served by your Voltrus instance lives at `http://<server>:3000/api/docs`,
with the raw OpenAPI spec at `/api/v1/openapi.json`. The SDKs' request and response types
are modeled directly on that spec.

## License

[MIT](LICENSE)
