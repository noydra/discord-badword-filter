# discord-badword-filter

discord-badword-filter is a Node.js module that can be used to automatically filter out bad words in messages sent on a Discord server.

## Installation

To install discord-badword-filter, run the following command:

```bat
npm install discord-badword-filter
```

## Usage

Here is an example of how to use discord-badword-filter in a Discord bot:

```js
const { Client, GatewayIntentBits } = require("discord.js"); 
const client = new Client({intents: [ GatewayIntentBits.GuildMessages ]});
const { filterMessage } = require('discord-badword-filter');

client.on('ready', () => {
  console.log(`Logged in as ${client.user.tag}!`);
});

client.on('messageCreate', (msg) => {
  const filteredContent = filterMessage(msg.content);

  if (filteredContent !== msg.content) {
    msg.channel.send(`${msg.author} Warning, avoid from the bad word usage.`);
  }
});

client.login('YOUR_DISCORD_BOT_TOKEN');

```

In this example, we are using the filterMessage function to filter out bad words from the message content. If any bad words are found, we send a message to the same channel, notifying the user that they cannot use bad words in the server.

Note that this is just a simple example, and you can modify the behavior of the filter to suit your needs.

## License
discord-badword-filter is released under the [MIT License](https://opensource.org/licenses/MIT).

## Contributing
If you have any suggestions, bug reports, or feature requests, please feel free to open an issue or submit a pull request on the GitHub repository. We welcome contributions from anyone who wants to improve this module.
