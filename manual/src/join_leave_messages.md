# Join/Leave Messages

To know if someone has joined your server, you need to connect to the Discord
gateway. Additionally, you will also need to enable the "server members intent"
for you application.

Visit the
[Discord Developer Portal](https://discord.com/developers/applications) to find
your application, and then click "Bot." You may or may not have to scroll down
to find the toggle.

![](./assets/join_leave_messages_0.png)

To connect to the gateway, you must use
[`core/gateway`](https://github.com/apacheli/whirlybird/tree/dev/core/gateway).

In your `deps.ts` file:

```ts
export * from "https://github.com/apacheli/whirlybird/raw/dev/core/gateway/mod.ts";
```

You will receive two events: `GUILD_MEMBER_ADD` and `GUILD_MEMBER_REMOVE`. In
your `handleEvent` function, create a case for both of these events:

```ts
const handleEvent: HandleEvent = (payload) => {
  switch (payload.t) {
    case GatewayEvents.GuildMemberAdd: {
      // ...
      break;
    }

    case GatewayEvents.GuildMembeRemove: {
      // ...
      break;
    }

    case GatewayEvents.MessageCreate: {
      // ...
      break;
    }
  }
};
```

To send a message, you can use
[`core/http`](https://github.com/apacheli/whirlybird/tree/dev/core/http).

In your `deps.ts` file:

```ts
export * from "https://github.com/apacheli/whirlybird/raw/dev/core/gateway/mod.ts";
export * from "https://raw.githubusercontent.com/apacheli/whirlybird/dev/core/http/mod.ts";
```

Next, specify the ID of the channel you want to send join/leave messages to.
Replace `<CHANNEL_ID>` with your desired channel's ID.

```ts
const channelId = "<CHANNEL_ID>";
```

In each of the cases, create a message to the specified channel:

```ts
    case GatewayEvents.GuildMemberAdd: {
      const member = payload.d;

      await http.createMessage(channelId, {
        content: `Welcome, ${member.user.username}.`,
      });
      break;
    }

    case GatewayEvents.GuildMembeRemove: {
      const member = payload.d;

      await http.createMessage(channelId, {
        content: `Goodbye, ${member.user.username}.`,
      });
      break;
    }
```

When connecting to the gateway, you must include the `GUILD_MEMBERS` intent to
receive these events.

```ts
const gateway = new GatewayClient(token, {
  handleEvent,
  intents: GatewayIntents.GuildMessages | GatewayIntents.GuildMembers,
  url: "wss://gateway.discord.gg?v=9",
});
```

Congratulations! Your bot should now send a message whenever someone joins or
leaves your server!
