# About

An update notification script for [AsusWRT-Merlin](https://www.asuswrt-merlin.net/) based on the [example script](https://github.com/RMerl/asuswrt-merlin.ng/wiki/Update-Notification-Example), which is run when there is a new version ([checked every 48 hours at 2 am with a random offset](https://github.com/RMerl/asuswrt-merlin.ng/blob/f32e73d911c839ad43937e28003509e3c011ba75/release/src/router/rc/watchdog.c#L7017)).

# Configuration

Enable the service you would like to recieve notifications on (e.g. Telegram):

```sh
# Enable/Disable (Default: Disable)
TELEGRAM="enable"
```

## Telegram

- `BOT_TOKEN`

This is the token for the bot. It is provided in the creation of a bot by following the steps provided in the [Telegram bot API documentation](https://core.telegram.org/bots#3-how-do-i-create-a-bot).

- `CHAT_ID` 

This is the unique identifier for the target chat. It can be obtained by messaging the bot and executing the following command (replace `$BOT_TOKEN`). The ID may be found at `"chat": {"id": 12345678},`:

```sh
curl https://api.telegram.org/bot$BOT_TOKEN/getUpdates | python -m json.tool
```

# Installation

1. Copy `update-notification` into `/jffs/scripts/`. For example:

```sh
scp update-notification root@192.168.1.1:/jffs/scripts/
```

2. Apply execute permissions to the script.

```sh
chmod +x /jffs/scripts/update-notification
```
