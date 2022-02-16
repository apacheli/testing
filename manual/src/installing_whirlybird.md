# Installing whirlybird

Installing whirlybird into your program is as simple as importing the core
modules directly into your code. To clarify the README, whirlybird is not a
module itself but a collection of modules. There is no central import location.
Instead, you must import each of the modules individually.

[See the Deno manual](https://deno.land/manual/examples/manage_dependencies) to
learn how to manage dependencies.

[`core/gateway`](https://github.com/apacheli/whirlybird/tree/dev/core/gateway)
and [`core/http`](https://github.com/apacheli/whirlybird/tree/dev/core/http) are
generally recommended for most end-users. These two modules expose the main
functionality of most bots.

In your `deps.ts` file:

```ts
export * from "https://github.com/apacheli/whirlybird/raw/dev/core/gateway/mod.ts";
export * from "https://github.com/apacheli/whirlybird/raw/dev/core/http/mod.ts";
```

In your `main.ts` file:

```ts
import { GatewayClient, HttpClient } from "./deps.ts";
```

`GatewayClient` and `HttpClient` is what you're most likely to use in your
program. However, you're free to import any additional whirlybird modules as
long as it suites your needs. You can skip ahead to the
[Core Modules](./core_modules.md) section of this manual to see the available
exports.
