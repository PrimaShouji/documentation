# Scheduling System

## Announce

The announcement system (Announce) is used for nearly all schedulable content - Delubrum Reginae, Zadnor, Bozja, and social events. It's integrated with Google Calendar, so you can view upcoming events in your calendar application of choice.

### Understanding announcements

![](../.gitbook/assets/announce\_example\_1.png)

Announcements have the following elements, in this order:

* The message ID of the message used to schedule the event
* The host of the event
* The event time, shown in **your system's time zone**
* The event description, which may be cut off if it's too long
* A link to copy the event to your calendar, if you don't already have the whole calendar saved
* A link to the event message
* The message ID of the message used to schedule the event (again)
* The event time (again), shown in your system's time zone
* A button you can press to get a notification half an hour before the event starts

Each announcement channel has its events sorted: the soonest event is at the bottom of the channel, and the event furthest in the future is located at the top of the channel.

### Announcing events

To announce an event, use `~announce EventDateAndTime | EventDescription` in the appropriate scheduling channel for your event type. Currently, `EventDateAndTime` _must_ be in Pacific Time, with a `MM/DD` date format. Even if you specify a different time zone, your input will be interpreted as PT. Event descriptions can span multiple lines - just press Shift+Enter to create a new line without sending the command. This command will create a Discord embed in the corresponding schedule channel, and create an event on the appropriate Google Calendar.

![](../.gitbook/assets/announce\_example\_0.png)

![](../.gitbook/assets/announce\_example\_1.png)

If you would like to schedule an event for the following year, extend the date to include the year, in `MM/DD/YYYY` format. If you leave off the year, the bot will assume you are scheduling an event in the current year.

30 minutes before your event begins, you and anyone who clicks the notification button on your event's announcement will be DM'd with a reminder that your event is starting soon. As the event host, you will be given the **Current Host** and **Run Pinner** roles, which temporarily give you access to additional event commands. If you are hosting a Delubrum Reginae (Savage) run, you will also be given the **Delubrum Roler** role. All of these roles will be granted for 4.5 hours.

#### Event host commands

`~setroler @User`: Temporarily grants the **Delubrum Roler** and **Run Pinner** roles to the specified user.

`~setpriority @User`: Temporarily makes a user a priority speaker in voice channels. This is useful for raid settings, where it is helpful to make a caller easier to be heard over others.

`~removepriority @User`: Removes priority speaker permissions from a user.

`~mute @User`: Mutes the voice communications of a user for 3 hours, or until they are unmuted.

`~unmute @User`: Unmutes a previously-muted user.

#### Run Pinner commands

`~pin`: Temporarily pins a message in a run channel. You can either provide the message to be pinned as a message link, or you can use the command while using the Reply feature on a message. Messages will be pinned for 4.5 hours.

`~unpin`: Unpins a message that was pinned using the \~pin command.

#### Delubrum Roler commands

For the following commands, the supported progression roles are:

* Trinity Seeker Progression
* Queen's Guard Progression
* Trinity Avowed Progression
* The Queen Progression

`~addprogroles FFLogsLink`: Adds progression roles for an entire raid according to the provided FFLogs link. Non-Rolers can also use this command in order to get roles for runs that were done outside of the server.

`~addprogrole @User RoleName`: Adds a progression role, and any previous progression roles, to a user. You can also provide multiple users in order to avoid using the command multiple times.

`~removeprogrole @User RoleName`: Removes a progression role from a user. You can also provide multiple users in order to avoid using the command multiple times.

### Cancelling events

To remove an announcement that you have created, use the `~unannounce` command. There are two variants of this command: One which takes the event's date and time, and another which takes your `~announce` command's message ID.

The version of this command that takes your event's date and time works similarly to the `~announce` command. Just use the command, and your event will be updated in the schedule channel and removed from the Google Calendar.

![](../.gitbook/assets/unannounce\_example\_0.png)

If you've scheduled multiple events at the same date and time, a prompt will be given for you to specify which event you would like to cancel. Simply send the number of the event you would like to cancel in order to continue.

![](../.gitbook/assets/unannounce\_example\_3.png)

To use the message ID variant of this command, use the message ID of your `~announce` message. The message ID of your `~announce` message can be found [right above](scheduling-system.md#understanding-announcements) the announcement.

![](../.gitbook/assets/unannounce\_example\_2.png)

When an event is cancelled, its corresponding announcement will be updated to show that the event was cancelled. The announcement will then eventually be removed.

![](../.gitbook/assets/unannounce\_example\_1.png)

### Rescheduling events

To reschedule an event that you have created, use the `~reannounce` command. This takes two options: an identifier for your event (either a date and time or the message ID of your `~announce` command), and the date and time you would like to reschedule your event to.

![](../.gitbook/assets/reannounce\_example\_0.png)

This will update both the embed in the schedule channel, and the corresponding event in the Google Calendar.

![](../.gitbook/assets/reannounce\_example\_1.png)

If you use this command with a run date and time as the first option, and you have multiple events scheduled at that date and time, a prompt will be offered for you to specify which of your events you would like to reschedule.

![](../.gitbook/assets/reannounce\_example\_2.png)

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

###

## Schedule

Schedule is a legacy system used solely for Baldesion Arsenal scheduling. It is integrated with Google Sheets, and has some more restrictions to reflect the nature of the content. The Announce system's commands are reflections of the Schedule system's commands.

### System restrictions

The following restrictions are in place for the legacy scheduling system:

#### Time blocks

All events are scheduled to take 3 hours and cannot overlap, due to the fact that concurrent runs are difficult to set up.

#### Available date range

Run dates must be within the next 28 days, as that is the number of columns set in the Google Sheet.

### Commands

The Announce system commands are largely simplified versions of this system's commands.

#### Scheduling an event

`~schedule Identifier DateAndTime OptionalMultiplier | Description`: Schedules an event at the specified date and time. `OptionalMultiplier` allows one to schedule multiple time blocks at once, if it is provided. This parameter should be provided as a number with an x before it, such as `x2` to schedule two back-to-back runs, or `x3` to schedule three at once.

`Identifier` is used to specify the run type. Valid options are:

* FR: Fragment/learning runs
* OP: Ozma progression runs
* OZ: Ozma clear runs
* RC: Ozma reclear runs
* EX: Nonstandard runs

#### Cancelling an event

`~unschedule DateAndTime`: Cancels the event at the provided date and time.

#### Rescheduling an event

`~reschedule CurrentDateAndTime | NewDateAndTime`: Reschedules an event that is currently at the first time, to the second time.
