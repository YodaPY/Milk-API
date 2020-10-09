# Milk-API
The Documentation for the Milk discord bot API

## Table of contents
* About Milk
* Endpoints
* Examples
  * Python
 
 
 ## About Milk
 Milk is a feature-rich discord bot, supporting features like verification, economy, leveling, image manipulation, custom commands, message and image filters as well as its own developer API. It's fully configureable and user friendly.

![Milk](https://cdn.discordapp.com/avatars/719243473437327420/ed8d87fb55fa79a213ca8d5da20eacaf.png?size=1024)

## Endpoints
Method | Endpoint | Arguments | Parameters
-------|----------|-----------|------------
GET | /leveling/users/user | guild_id: int - user_id: int | None
GET | /leveling/users/leaderboard | guild_id: int | None
GET | /leveling/users/leaderboard | None | None
GET | /economy/users/user | user_id: int | None
GET | /economy/users/leaderboard | None | None

## Examples

#### /leveling/users/user

```json
{
  "user": {
    "User ID": ID,
    "Guild ID": ID,
    "XP": 18557,
    "Fake XP": 1930
  }
}
```

```py
from aiohttp import request

async def get_user():
  async with request("GET", "/leveling/users/user/user_id") as resp:
    data = await resp.json()
    return data
```

#### /leveling/users/leaderboard

```json
{
  "Guild ID": ID,
  "leaderboard": [
    {
      "ID": 20487
    }
  ]
}
```

```py
from aiohttp import request

async def get_user():
  async with request("GET", "/leveling/users/leaderboard/guild_id") as resp:
    data = await resp.json()
    return data
```
