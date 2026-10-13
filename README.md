# 🌐 ProTranslate

A Discord bot that translates new messages using AI that understands **slang**, so "E aí" becomes "Yo" instead of "And there".

> Yes, this bot is vibe coded. It's open source, so feel free to improve it.

**Website:** https://pro-translate.duckdns.org/

## Features

- Translates the meaning and the vibe, not word for word
- Works with any language (100+ suggested while typing)
- Only translate one language into another (`/target`)
- Skip languages you don't want translated (`/notarget`)
- `/translate` works any time, even when auto-translating is off
- Only translates **new** messages, and only after `/run`
- Shows a loading gif while translating (needs the Embed Links permission)
- Free AI: Google Gemini free tier, with OpenRouter free models as backup

## Commands

| Command | What it does |
| --- | --- |
| `/run` | Start translating new messages |
| `/stop` | Stop translating |
| `/target target:Spanish to:English` | Only translate one language into another |
| `/notarget language:English` | Never translate a language (run again to turn it back on) |
| `/translate text:... translate:English` | Translate a text, works even if the bot isn't running |
| `/vibecode` | Is this bot vibe coded? |
| `/web` | Link to the website |
| `/vote` | Vote on top.gg |
| `/creator` | Who made the bot |

`/run`, `/stop`, `/target` and `/notarget` need the **Manage Server** permission.

## Run it yourself

1. Install [Node.js](https://nodejs.org) 18 or newer.
2. Create a bot at the [Discord Developer Portal](https://discord.com/developers/applications). Under **Bot**, turn on **Message Content Intent**.
3. Copy `.env.example` to `.env` and fill it in (at least `DISCORD_TOKEN` and one AI key).
4. Get a free Openrouter Key (https://openrouter.ai/keys).
5. Run:

```bash
npm install
npm start
```

The console should say `Registered 9 commands`.

**Bot permissions needed:** View Channels, Send Messages, Read Message History, Embed Links.

### Options (in `.env`)

| Variable | What it does |
| --- | --- |
| `DISCORD_TOKEN` | Your bot token (required) |
| `OPENROUTER_API_KEY` | AI key (required) |
| `GEMINI_MODELS` / `OPENROUTER_MODELS` | Models to try, in order |
| `WEBSITE_URL` | Link sent by `/web` |
| `GUILD_ID` | Test server ID. Commands update instantly, but only in that server |
| `CREATOR_ID` | Discord user ID shown by `/creator` |

Slash commands can take up to an hour to show up globally. Use `GUILD_ID` while testing.

## Privacy

Message text is sent to the AI provider (Google Gemini or OpenRouter) to be translated. Free tiers of AI services may use submitted text to improve their products, so don't use this for private chats. See [the privacy policy](https://pro-translate.duckdns.org/privacy.html).

## ⚠️ Never commit your secrets

Your `.env` file holds your bot token and API keys. It is in `.gitignore` on purpose. If you ever leak a token, reset it right away in the Developer Portal.

## Contributing

Pull requests and issues are welcome.

## License

[MIT](LICENSE)
