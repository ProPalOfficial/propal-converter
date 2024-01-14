# propal-converter
Count the number of conversions based on the provided formula.

## Installation
```bash
npm install propal-converter
```
## Usage
```js
const countConversions = require('propal-converter');

const probotCredits = 100; // Replace with the actual number of probot credits

const propalAmount = countConversions(probotCredits);

console.log('Propal Amount:', propalAmount);
```
## Example with Discord.js Bot
```js
const Discord = require('discord.js');
const countConversions = require('propal-converter');

const client = new Discord.Client();

client.on('message', (message) => {
  if (message.content.startsWith('!convertCredits')) {
    const args = message.content.split(' ');
    if (args.length === 2) {
      const probotCredits = parseFloat(args[1]);
      if (!isNaN(probotCredits)) {
        const propalAmount = countConversions(probotCredits);
        message.channel.send(`Propal Amount: ${propalAmount}`);
      } else {
        message.channel.send('Invalid input. Please provide a valid number of probot credits.');
      }
    } else {
      message.channel.send('Invalid command. Usage: `!convertCredits <probotCredits>`');
    }
  }
});

client.login('YOUR_BOT_TOKEN');
```
