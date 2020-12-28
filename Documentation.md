# Milk-API
The Documentation for the Milk discord bot API

## Table of contents
* About Milk
* Endpoints
* Examples
  * Python
 
 
 ## About Milk
 Milk is a feature-rich discord bot, supporting features like verification, economy, leveling, image manipulation, custom commands, message and image filters as well as its own developer API. It's fully configureable and user friendly.

![Milk](https://cdn.discordapp.com/attachments/339112602867204097/793157816327602206/b4c41895986e598e443e8d99a500e48b.png)

## Endpoints
Method | Endpoint | Additional query
-------|----------|------------------
GET | /leveling/users/user/<guild_id>/<user_id> | None
GET | /leveling/users/leaderboard/<guild_id> | limit, reversed
GET | /leveling/users/leaderboard | limit, reversed
GET | /economy/users/user/<user_id> | None
GET | /economy/users/leaderboard | limit, reversed
GET | /social/badges/<user_id> | None

For every request you sent you will need an Authorization Token:
Generate one with `milk.bot generate token`

### Examples

```py
from aiohttp import request

async with request(
    "GET",
    "http://milk.tmpod.dev/api/economy/users/leaderboard",
    headers={
        "Token": "My Token"
    }
) as resp:
    data = await resp.json()
```
