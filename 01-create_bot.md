# Create the Weather Bot

The first step to creating a bot with Bot Framework Composer is
creating a new bot project from the home screen. This will create a
new folder on your computer with all the files necessary to build, test and run the bot.

## Create Project

1. From the home screen, select `New` from the upper left corner.
You'll be presented with a dialog with options to either create an empty bot project from scratch, or to create one based on a template.

    For this workshop, make sure `Create from Scratch` selected and click `Next`

<img src="./assets/01/create-1.png" style="background-color:white" width = "800" />

2. The second screen asks for a `Name` and `Description` of your bot.

    Let's call it:
     ```
     weatherBot
     ```` 
     
     and give it a description:
     ```
     a friendly bot who can talk about the weather.
     ```

      > Make sure not to put any spaces or special characters in the bot's name.

      > Leave the `Location` field with its default value - this will put the bot project into Composer's default project folder where it will be easy to find.  

<img src="./assets/01/create-2.png" style="background-color:white" width = "800" />

3. Click `Next`, and Composer will create the project for you!


## Give your bot something to say

After creating your bot, Composer will load the new bot's `Main` dialog in the editor.  It should look like this:

<img src="./assets/01/empty-main-dialog.png" style="background-color:white" width = "800" />

Each dialog contains one or more `Triggers` that define the actions available to the bot while the dialog is active. Right now the dialog is empty, so the bot won't do anything.

As a refresher, here are the constituent parts of a dialog - 

<img src="./assets/01/adaptive-dialog-anatomy.png" style="background-color:white" width = "800" />

You will notice that the new bot is pre-configured with one trigger in the left dialogs window - `Handle ConversationUpdate`. 

> Triggers help your dialog capture events of interest and respond to them using actions.

1. Click the `Handle ConversationUpdate` trigger in the left hand explorer.

2. You will see a new flow has been added to the dialog. 

<img src="./assets/01/new-flow.png" style="background-color:white" width = "800" />

3. To help keep the bot organized, let's rename this trigger to something that describes what it does.

      In the `property editor` on the right side of the screen, click on the name of the trigger ("Handle ConversationUpdate"). You'll be able to update the title there, and the change will be instantly reflected in the dialog and navigation on the left.

      Rename ths trigger to:
      ```
      WelcomeTheUser
      ````

<img src="./assets/01/rename-trigger.gif" style="background-color:white" width = "800" />

Now, let's actually make the bot do something! 
Inside the flow, you'll see that the teal `Trigger` box has a line below it that includes in a "+" button.

The "+" button can be used to add `Actions` to the conversation flow. You can use this to add actions to the end of a flow, or insert actions at an earlier point.

For now, let's instruct the bot to send a simple greeting.

4. Click the "+" button and select the first menu item `Send Messages`, and then selec the first item from the sub-menu: `Send an Activity`

<center>
<img src="./assets/01/add-send-activity.gif" style="background-color:white" width = "400" />
</center>

5. Select the new `Send an Activity` action in the flow and it's properties will appear on the right hand side of the screen.  This action has only one main property - the text of the activity to send.

6. Type a welcome message into this field. It is always a good idea to have your bot introduce itself and explain it's main features.  So let's make the welcome message something like:

    ```
    Hi! I'm a friendly bot that can help with the weather. Try saying WEATHER or FORECAST.
    ```

Your bot should now look like this:

<img src="./assets/01/send-activity.png" style="background-color:white" width = "800" />

Next, let's temporarily disable the recognizer for the main dialog. We will get back to this in the next step.

7. Click on `WeatherBot.Main` in the left pane to bring up the properties editor for the root dialog.

6. In the property editor on the right hand side, click on `Recognizer type` and select `None`.

<center>
<img src="./assets/01/recognizer-none.png" style="background-color:white" width = "300" />
</center>

> Dialogs in Composer support 2 different recognizer types - LUIS, Regex. Unless you need intent classification or entity extraction, we can remove recognizer by setting it to `None`.

# Start your bot and test it

Now that our new bot has its first simple feature, let's launch it in the emulator and make sure everything works.

7. Click the `Start Bot` button in the upper right hand corner of the screen.  This tells Composer to launch the bot's runtime (an external app powered by the Bot Framework SDK) and updates it with the latest content and settings from Composer.

8. After a few seconds, a second link will appear next to the button thats `Test bot in emulator`.  Click this link to open Emulator and connect.

<center>
<img src="./assets/01/start-bot.gif" style="background-color:white" width = "400" />
</center>

You should see a window like this appear:

<img src="./assets/01/emulator-launch.png" style="background-color:white" width = "800" />

And the bot should immediately greet you with the message we just configured:

<center>
<img src="./assets/01/greeting-in-emulator.png" style="background-color:white" width = "300" />
</center>

We now have a working bot, and we're ready to add some more substantial functionality!

## Covered in this section
- Create a new bot project
- Add a trigger to a dialog
- Adding an action to a trigger
- Using the dialog flow editor, property editors
- Running the bot locally
- Testing the bot using Bot Framework Emulator