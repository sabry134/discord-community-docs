!!! danger
    Do not literally type out &lt;   &gt; [   ] \| etc

!!! info
    When referencing commands, Mod commands are in **bold**.

!!! tip
    This is a tip message.

!!! warning 
	This is a warning message.

!!! note
    This is a note message.

!!! important
    This is an important message.

!!! Custom
    This is a caution message.

!!! attention
    This is an attention message.





# Tags

!!! info
    Getting tags after they're created can be done without using !tag name simply do !name

Tags can get complicated, see [advanced tag usage](https://docs.carl.gg/tags-and-triggers/tags-advanced-usage/) for a more thorough explanation of the tagscript

### Tag Commands

???+ tldr "Tag Commands"
	| Name | Example | Usage |
	| :--- | :--- | :--- |
	| [tag get\|tag] &lt;lookup&gt; | !classdiscords | This is how you get tags after they're saved. |
	| tag [create\|add\|+] &lt;name&gt; &lt;content&gt; | !tag + test Hello world | Makes a tag named test with the content Hello world. |
	| tag [delete\|del\|remove\|-] &lt;tagname&gt; | !tag - test | Removes a tag |
	| tag ++ &lt;name&gt; &lt;pastebin link&gt; | !tag ++ setup https://pastebin.com/tehqxQRV | Since tags can have an output shorter than their length, using !tag ++ allows you to make them |
	| tag [+=\|append] &lt;tagname&gt; &lt;content&gt; | !tag += test and my mom | Adds content to an already existing tag |
	| tag [a\|alias] &lt;new&gt; &lt;existing&gt; | !tag alias testing test | Creates a link to an already existing tag, changes made to the original tag means the aliased tag will also be changed. The name you want for the alias is the first argument, the already existing tag is the second. |
	| tag raw &lt;name&gt; | !tag raw test | retrieves a tag with its markdown (bold, italic, tagscript etc.) removed. |
	| tag edit &lt;name&gt; &lt;content&gt; | !tag e test bye world | Edits the content of an already existing tag. |
	| **tag nsfw &lt;name&gt;** | !tag nsfw test | Restricts the tag so that it can only be used in channels marked as nsfw |
	| **tag restrict &lt;name&gt;** | !tag restrict test | To prevent big tags cluttering your chatty channels, this will make the bot post the content in the bot-channel and ping the author. |
	| tag stats [@member] | !tag stats @Carl#0080 | Shows information about the servers tags (uses, top 3, total number of tags). If you mention someone, it will show their tags instead. |
	| tag info &lt;name&gt; | !tag info test | Shows some stats collected about the tag, uses, creation date, last update, owner. |
	| **tag ownership** | !tag ownership | With this enabled (disabled by default) tags are 'owned' meaning that unless you're a mod, you can't edit, append or delete other people's tags (You can still create aliases to people's tags) |
	| **tag modonly** | !tag modonly | With this enabled, only mods can manage tags, non-mods can still use them. |
	| **tag prompt** | !tag prompt | Know how trying to create a tag that already exists asks you if you want to edit, or append? With this disabled (enabled by default) it will default to editing the tag |
	| tag claim &lt;name&gt; | !tag claim realms | Claims a tag from a member who has left the server, only relevant if ownership is enabled |
	| tag sub &lt;name&gt; &lt;from&gt; &lt;to&gt; | !tag sub invite discord.gg/abc123 discord.gg/xyz999 | Replaces every occurance of from\_string with to\_string in an already existing tag. This can be extremely useful for expired invite links, slightly outdated information, or anything else that allows you to systematically correct your mistakes. |
	| [tag list\|command\|taglist] | !taglist | Lists all of the tags on the server |
	| tag share &lt;name&gt; | !tag share picross | Creates a shareable link of a tag so that other users can import it to their servers. |

### Importing Tags

You can easily import tags from a tag's share link. After navigating to the link, find the server selection dropdown menu in the lower right-hand corner, select your server, then click "Import"


# Announcements

### Feeds

???+ info "What are feeds?"
	What are feeds? Feeds are a way for you to make announcements and ping a specific role without having to deal with the annoyances and potential abuse from having a mentionable role or manually toggling a role inbetween mentionable and not. You need Manage Server Discord permissions to use the feed commands.<br><br>A feed is an association between a role and a channel. When you use the feed announce command, the role will be set to mentionable very briefly, the role will be pinged and your message will be sent in the channel with which the feed is associated, and the role will subsequently be set back to unmentionable.

???+ tldr "Feed Commands"
	| Name | Example | Usage |
	| :--- | :--- | :--- |
	| **feed** | !feed | Lists all the feeds that have been set up in the server. |
	| **feed create &lt;name&gt; &lt;role&gt;** | !feed create got game of thrones | Creates a feed in the channel the command is used in with a specific name and a specific role that will be mentioned. |
	| **announce** | !feed announce got Hey guys, everyone dies | Makes an announcement to the specified feed. |
	| **feed \[delete\|-\|del\|remove\]** | !feed delete got | Deletes a feed. Note: This does not delete the associated role, so if you created one specifically for a feed, you need to delete it. |
	| **!feed clear** | !feed clear | Deletes ALL feeds from the server. |
	| **!feed move** | !feed move bot \#announcements | Moves a feed to a specified channel. Note: You need send messages permissions in the channel you move it to. |

### Autofeeds

Automatic feeds can be seen as group reminders, and they share a lot of functionality with reminders.

!!! tip
    Timezones suck, use the dashboard at [https://carl.gg](https://carl.gg) to create autofeeds with your local timezone.

???+ tldr "Autofeed Commands"
    The id argument is the autofeed id which the bot spits out when you create an autofeed or when you do `!af`

	| Name | Example | Usage |
	| :--- | :--- | :--- |
	| **\[af\|autofeed\]** | !af | Lists all autofeeds set up in the server. |
	| **autofeed &lt;role&gt; &lt;time&gt; &lt;message&gt;** | !autofeed "final fantasy xiv" 18h The servers have been reset, get out there! | Normal autofeeds \(the ones created by this command\) will ping the role  specified when setting them up. |
	| **autofeed silent &lt;time&gt; &lt;message&gt;** | !autofeed silent 2 hours Vote for carlbot on discord bots! | Like a normal autofeed except it does not have a role associated with it and thus, does not ping anything. |
	| **autofeed silence &lt;id&gt;** | !autofeed silence 37 | Silences an already existing normal feed. |
	| **autofeed repeat &lt;id&gt;** | !autofeed repeat 13 24h | Marks an autofeed to be repeated. This keeps going until you delete the autofeed. |
	| **autofeed remove &lt;id&gt;** | !autofeed remove 77 | Removes an autofeed |
	| **autofeed clear** | !af clear | Removes ALL autofeeds. |
	| **autofeed move &lt;id&gt; &lt;\#channel&gt;** | !autofeed move 73 \#general | Moves an autofeed to a specified channel. Note: You need send messages permissions in the channel you move it to. |



???+ tldr "Fortnite Stats"

	| Name | Example | Usage |
	| :--- | :--- | :--- |
	| [fortnite\|fn] [name] | !fortnite Dakotaz | Fetches some fortnite stats for a specified player (PC). |
	| fortnite [playstation\|ps4\|psn] [name] | !fn psn Upshall | Playstation version of the fortnite command. |
	| fortnite [xbox\|xbl] [name] | !fn xbox AlexRamiGaming | Xbox version of the fortnite command. |




???+ example "Punishments"

    The punishments available are:

    * **delete** - Deletes the message 
    * **warn** - Warns the offender 
    * **tempmute &lt;duration&gt;** - Temporarily mutes for the duration, format the time like 3h42m
    * **mute** - Indefinitely mutes 
    * **kick** - Kicks the offender 
    * **tempban &lt;duration&gt;** - Temporarily bans the offender for the duration 
    * **ban** - Bans the offender 
    * **defer** - Sends the context to the drama channel and lets mods vote on it 
    * **message** - Sends a message to the channel warning the member 
    * **dm/pm** - Sends a private message to the offender

    You can add more than one punishment by separating them with commas.


<!-- termynal -->

```
> pip install termynal
---> 100%
Installed
```