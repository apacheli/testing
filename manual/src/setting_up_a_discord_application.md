# Setting Up a Discord Application

You must create a Discord application before you can use whirlybird. To get
started, visit the
[Discord Developer Portal](https://discord.com/developers/applications).

If you are on the Discord homepage, scroll to the bottom and click "Developers"
listed under "Resources."

![](../assets/setting_up_a_discord_application_0.png)

Once you are there, click "Applications."

![](../assets/setting_up_a_discord_application_1.png)

Click "New Application." It will prompt you to input a name for your
application.

Click "Bot" and then click "Add Bot." It will open another prompt asking if you
want your application to become a bot. Confirm by clicking "Yes, do it!"

![](../assets/setting_up_a_discord_application_2.png)

Next, head over to the "OAuth2" section and click "URL Generator." It will allow
you to invite your application into a server.

![](../assets/setting_up_a_discord_application_3.png)

Enable the `bot` scope. You can also optionally enable the
`application.commands` scope if you need application commands (such as slash
commands). That will be for a later topic in this manual. If you're interested,
continue reading!

![](../assets/setting_up_a_discord_application_4.png)

At the bottom will be your generated URL. When you visit the URL, it will prompt
an application invitation. Select the desired server you wish to add your
application, and then click "Authorize."

Congratulations! You've successfully set up your Discord application! It will
appear as offline as no program is currently running the bot. Continue reading
to learn how whirlybird can get your bot online.
