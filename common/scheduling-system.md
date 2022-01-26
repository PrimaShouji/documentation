# Scheduling System

Prima has not just one, but two scheduling systems: Announce and Schedule.

## Announce

Announce is used for nearly all schedulable content - Delubrum Reginae, Zadnor, Bozja, and social events. It's integrated with Google Calendar, so you can view upcoming events in your calendar application of choice.

### Understanding announcements

Explanation of announcement embed format

### Announcing events

To announce an event, use `~announce EventDateAndTime | EventDescription` in the appropriate scheduling channel for your event type. Currently, `EventDateAndTime` _must_ be in Pacific Time, with a `MM/DD` date format. Even if you specify a different time zone, your input will be interpreted as PT. This command will create a Discord embed in the corresponding schedule channel, and create an event on the appropriate Google Calendar.

Image

If you would like to schedule an event for the following year, extend the date to include the year, in `MM/DD/YYYY` format. If you leave off the year, the bot will assume you are scheduling an event in the current year.

30 minutes before your event begins, you and anyone who clicks the notification button on your event's announcement will be DM'd with a reminder that your event is starting soon. As the event host, you will be given the Current Host and Run Pinner roles, which temporarily give you access to additional event commands.

#### Event host commands

Some stuff

### Cancelling events

To remove an announcement that you have created, use the `~unannounce` command. There are two variants of this command: One which takes the event's date and time, and another which takes your `~announce` command's message ID.

Image

The version of this command that takes your event's date and time works similarly to the `~announce` command. Just use the command, and your event will be updated in the schedule channel and removed from the Google Calendar.

Image

If you've scheduled multiple events at the same date and time, a prompt will be given for you to specify which event you would like to cancel. Simply send the number of the event you would like to cancel in order to continue.

Image

The command can also be used with the message ID of your `~announce` command message:

Image

### Rescheduling events

To reschedule an event that you have created, use the `~reannounce` command. This takes two options: an identifier for your event (either a date and time or the message ID of your `~announce` command), and the date and time you would like to reschedule your event to.

Image

This will update both the embed in the schedule channel, and the corresponding event in the Google Calendar.

Image

If you use this command with a run date and time as the first option, and you have multiple events scheduled at that date and time, a prompt will be offered for you to specify which of your events you would like to cancel.

### Saving community calendars

All calendar links end with a time zone written in their URLs, usually at their end. You can recognize the time zone in a URL by the text `ctz=` immediately preceding it.

![An example URL. Note the ctz=America/Los\_Angeles at the end of the URL.](../.gitbook/assets/google\_calendar\_url\_time\_zone.png)

Google Calendar uses time zone names as defined by the [tz database](https://en.wikipedia.org/wiki/List\_of\_tz\_database\_time\_zones). To adjust how events are displayed, replace `America/Los_Angeles` with the appropriate label from the **TZ database name** column of the table on the linked Wikipedia page.

You can add a community calendar to your own Google Calendar using the **+ Google Calendar** button at the bottom-right of the webpage.

![](../.gitbook/assets/google\_calendar\_add\_button.png)

Clicking this button will take you to your own Google Calendar and give you an option to add the community calendar to your own calendar set.

If you would like to then save a calendar to an external application, click the settings button under the **Other calendars** section of the interface.

![](../.gitbook/assets/google\_calendar\_settings.png)

From here, scroll down to the **Integrate calendar** section and copy the text under **Public address in iCal format**. Refer to your calendar application's documentation to use this address to finish integrating the calendar.

![The relevant address is located at the bottom of this settings section.](../.gitbook/assets/google\_calendar\_integration.png)

## Schedule

Schedule is a legacy system used solely for Baldesion Arsenal scheduling. It is integrated with Google Sheets, and has some more restrictions to reflect the nature of the content. The Announce system's commands are reflections of the Schedule system's commands.
