# Setting Up a Discord Application

You must create a Discord application before you can use whirlybird. To get
started, visit the
[Discord Developer Portal](https://discord.com/developers/applications).

If you are on the Discord homepage, scroll to the bottom and click "Developers"
listed under "Resources."

![](https://user-images.githubusercontent.com/43933794/146304369-6a9df300-ee0c-4a2c-9628-0a8c95c18e44.png)

Once you are there, click "Applications."

![](https://user-images.githubusercontent.com/43933794/154184237-f474b672-4710-4c7e-82c9-019b9ba33d4e.png)

Click "New Application." It will prompt you to input a name for your
application.

Click "Bot" and then click "Add Bot." It will open another prompt asking if you
want your application to become a bot. Confirm by clicking "Yes, do it!"

![](https://user-images.githubusercontent.com/43933794/146304714-3a624b7d-cf72-4e26-a878-08898344c342.png)

Next, head over to the "OAuth2" section and click "URL Generator." It will allow
you to invite your application into a server.

![](https://user-images.githubusercontent.com/43933794/154183202-87cdd381-2445-4a42-998a-d53dfbe8104e.png)

Enable the `bot` scope. You can also optionally enable the
`application.commands` scope if you need application commands (such as slash
commands). That will be for a later topic in this manual. If you're interested,
continue reading!

![](https://user-images.githubusercontent.com/43933794/146305897-35fc9924-02b2-4ed9-92ab-59ac431b1d9a.png)

At the bottom will be your generated URL. When you visit the URL, it will prompt
an application invitation. Select the desired server you wish to add your
application, and then click "Authorize."

Congratulations! You've successfully set up your Discord application! It will
appear as offline as no program is currently running the bot. Continue reading
to learn how whirlybird can get your bot online.
