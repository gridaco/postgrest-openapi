# postgrest-openapi

JS postgREST OpenAPI Spec parser.

A Library for parsing the openapi spec and re-constructing the relational graph and the column infos.

> This is not a request library, for making requests to a postgREST server, use [postgrest-js](https://github.com/supabase/postgrest-js)

### (WIP)

> This is a placeholder repo, we are working on exporting the related code as a package from [hrere](https://github.com/gridaco/grida/blob/main/apps/forms/lib/supabase-postgrest/parse.ts).

## Usage

```bash
npm install postgrest-openapi
yard add postgrest-openapi
pnpm add postgrest-openapi
```

Fetching the OpenAPI spec from a postgREST server:

```ts
import { url } from "postgrest-openapi";
const json = await fetch(
  url("https://xxxxxxxxxx.supabase.co/rest/v1", {
    apiKey: "xxxxxxxxxx", // your anon key (anon key can fetch the spec just fine)
  })
).then((res) => res.json());
```

Parsing

```ts
import Parser from "postgrest-openapi";

const parser = new Parser(json);

const definition = parser.define();
```
