# Using Environment Variables

The recommended way of storing your bot's token is by using environment
variables. You should not hard code your bot's token directly into your program.

```sh
BOT_TOKEN=""
```

In your `main.ts` file:

```ts
const token = `Bot ${Deno.env.get("BOT_TOKEN")}`;
```

You must enable `--allow-env` to use environment variables.

```ts
$ BOT_TOKEN="" deno run --allow-net main.ts
```

You can also use `prompt` if you forget to set an environment variable when
running your program from the CLI.

```ts
let token = Deno.env.get("BOT_TOKEN") ?? prompt("bot token:");
if (!token) {
  throw new Error("Missing token");
}
token = `Bot ${token}`;
```

Optionally, you can use another third party module to automatically load the
environment variables for you.

[See the Deno manual](https://deno.land/manual/getting_started/permissions#environment-variables)
for additional details.
