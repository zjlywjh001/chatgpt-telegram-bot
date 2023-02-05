# ChatGPT Telegram Bot

![badge:version](https://img.shields.io/badge/version-1.0.5-brightgreen)
![license](https://img.shields.io/badge/license-MIT-green)

A ChatGPT bot for Telegram based on Node.js. <del> Works with Cloudflare protection.</del> Replace ChatGPT API to 4.1.1 which use official chatGPT api.

## Features

<table>
  <tr>
    <th>Private Chat</th>
    <th>Group Chat</th>
  </tr>
  <tr>
    <td><img src="./assets/private_chat.jpg" /></td>
    <td><img src="./assets/group_chat.jpg" /></td>
  </tr>
</table>

- Support for both private and group chats
- Work in privacy mode (the bot can only see specific messages)
- Bot access control based on user and group IDs
- Reset chat thread and refresh session with command
- Typing indicator, Markdown formatting, ...
- Cloudflare bypassing and CAPTCHA automation
- User-friendly logging

## Usage

### Start the server

> **Note** This bot uses a [browser-based ChatGPT API](https://github.com/transitive-bullshit/chatgpt-api), please make sure you have Node.js >= 18 <del> and a Chromium-based browser installed.</del->

To get started, follow these steps:

1. Make a copy of the file `.env.example` and rename it as `.env`.         
2. <del>In the `.env` file, enter your OpenAI account information and Telegram bot token. Set `IS_GOOGLE_LOGIN` to `true` if you're using Google auth.</del>           
3. Specify the ID of the users and groups who are permitted to use this bot. Separate multiple IDs with commas (`,`). Note that all members of the specified groups will have access to the bot inside the group. **If you leave these options empty, every person and group will be able to use the bot.**           
4. <del>If the browser is not installed in the default location, specify its executable path. You can also specify proxy settings, if needed.</del>           
5. <del>Specify the `NOPECHA_KEY` or `CAPTCHA_TOKEN` if you're using the corresponding CAPTCHA solver.</del>           
6. You can also specify the command to invoke the bot in group chats. The default command is `/chat`.           
7. <del>Set `IS_PRO_ACCOUNT` to `true` if you're using a premium / pro / paid account. </del>              
8. Specify the `OPENAI_API_KEY` of your openai platform account.       

Then you can start the bot with:

```shell
pnpm install
pnpm build && pnpm start
```

### Chat with the bot in Telegram

To chat with the bot in Telegram, you can:

- Send direct messages to the bot (this is not supported in groups)
- Send messages that start with the specified command (e.g., `/chat` or the command you specified in the `.env` file)
- Reply to the bot's last message

> **Note** Make sure you have enabled the privacy mode of your bot before adding it to a group, or it will reply to every message in the group.

The bot also has several commands.

- `/help`: Show help information.
- `/reset`: Reset the current chat thread and start a new one.
- `/reload` (admin required): Refresh the ChatGPT session.

> **Note** When using a command in a group, make sure to include a mention after the command, like `/help@chatgpt_bot`.


## Advanced

### Running the bot on a headless server     

No need browser session now.     
      

#### Docker

You can also try this docker image by running the following command from the project root folder:

```shell
docker compose up
```

## LICENSE

[MIT License](LICENSE).

## Credits

- [ChatGPT API](https://github.com/transitive-bullshit/chatgpt-api): Node.js client for the unofficial ChatGPT API.
- [Node.js Telegram Bot API](https://github.com/yagop/node-telegram-bot-api): Telegram Bot API for NodeJS.
- [🤖️ chatbot-telegram](https://github.com/Ciyou/chatbot-telegram): Yet another telegram ChatGPT bot.
