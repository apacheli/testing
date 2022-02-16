# Built-In Logging

whirlybird automatically logs events to the terminal by default. If you wish to
use the logger, you can import it from
[`core/util`](https://github.com/apacheli/whirlybird/tree/dev/core/util).

In your `deps.ts` file:

```ts
export * from "https://github.com/apacheli/whirlybird/raw/dev/core/util/mod.ts";
```

Logger levels:

- `debug`: A general message about an operation.
- `error`: An error has occurred, but the program can still operate.
- `fatal`: A fatal error has occurred, and the program should probably exit.
- `info`: A general message about an operation that executed successfully.
- `trace`: A message about an operation at the finest details.
- `warn`: Something unintentional may have happened. It can usually be ignored.

whirlybird also provides ANSI colors. Some operating systems or source-code
editors may not support every color. However, this should mostly benefit your
use cases.

In your `main.ts` file:

```ts
import {
  ansi,
  logger,
} from "https://github.com/apacheli/whirlybird/raw/dev/core/util/mod.ts";

logger.info(ansi.yellow(`Woah, this message is yellow!`));
```

You can also use the `ansi` export for Discord messages. You must use a code
block. This is a relatively new feature, so it may not show up correctly across
all clients.

```ts
await http.createMessage(channelId, {
  content: `\`\`\`ansi\n${ansi.green("I am groot")}\n\`\`\``,
});
```
