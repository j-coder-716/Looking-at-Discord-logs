# Looking-at-Discord-logs
Project: Dealing with Discord logs


The JSON file discord_logs.json contains a log of activities

Here is a fragment of this file. The highlighted lines contain information that the user Sean joined the voice channel ‘General Voice’ on March 4, 2021 at 21:45:38 GMT:

{'id': '817150823247118356',
   'type': 'Default',
   'timestamp': '2021-03-04T21:45:38.19+00:00',
   'timestampEdited': None,
   'isPinned': False,
   'content': '',
   'author': {'id': '803346258977882163',
    'name': 'ProBot ✨',
    'discriminator': '0000',
    'isBot': True,
    'avatarUrl': 'https://cdn.discordapp.com/embed/avatars/1.png'},
   'attachments': [],
   'embeds': [{'title': '',
     'url': None,
     'timestamp': '2021-03-04T21:45:38.052+00:00',
     'description': '**@Unknown joined voice channel  `General Voice` .**',
     'author': {'name': 'Sean',
      'url': None,
      'iconUrl': 'https://cdn.discordapp.com/embed/avatars/1.png'},
     'footer': {'text': 'MTH 448/548'},
     'fields': []}],
   'reactions': []}
 
Here is another fragment. This one shows that the user Jamya left the voice channel ‘voice xray’ on January 25 2021 at 20:57:58 GMT:

{'id': '803368089449136188',
   'type': 'Default',
   'timestamp': '2021-01-25T20:57:58.382+00:00',
   'timestampEdited': None,
   'isPinned': False,
   'content': '',
   'author': {'id': '803346258977882163',
    'name': 'ProBot ✨',
    'discriminator': '0000',
    'isBot': True,
    'avatarUrl': 'https://cdn.discordapp.com/embed/avatars/1.png'},
   'attachments': [],
   'embeds': [{'title': '',
     'url': None,
     'timestamp': '2021-01-25T20:57:58.186+00:00',
     'description': '**@Unknown left voice channel  `voice xray` .**',
     'author': {'name': 'Jamya', 
      'url': None,
      'iconUrl': 'https://cdn.discordapp.com/embed/avatars/1.png'},
     'footer': {'text': 'MTH 448/548'},
     'fields': []}
 
Objectives
Part 1
Use the log file to create a pandas DataFrame with the record of all occurrences when a user either left or joined a voice channel. The DataFrame should have three columns:

the column “name” should contain names of users

the column “event” should record if a user joined or left a channel

the column “time” should give the time of each event.

The rows of the DataFrame should be ordered according to times of events: from the earliest to the latest.

Here is a sample of showing the structure of the DataFrame:

channels_df.tail(5)

name	event	time

627	Jasmin	left	2021-03-27 16:43:51.750000+00:00

628	Ariana	joined	2021-03-28 19:02:10.440000+00:00

629	Kathy	joined	2021-03-28 19:02:10.899000+00:00

630	Kathy	left	2021-03-28 19:20:37.529000+00:00

631	Ariana	left	2021-03-28 19:20:40.083000+00:00

Part 2
For each user compute the total time the user spent in voice channels. Here is a sample of results you should obtain:

times_df.tail(5)

name	time_in_channels

25	Ariana	0 days 17:37:12.113000

26	Jamya	1 days 01:12:34.347000

27	Kathy	1 days 03:15:31.871000
28	Edward	1 days 19:39:40.461000
29	Abagail	3 days 22:22:09.153000
