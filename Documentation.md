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
GET | /leveling/users/leaderboard | guild_id: int | limit
GET | /leveling/users/leaderboard | None | limit
GET | /economy/users/user | user_id: int | None
GET | /economy/users/leaderboard | None | limit

## Examples

#### /leveling/users/user

```json
{
  "user": {
    "User ID": 12345,
    "Guild ID": 12345,
    "XP": 18557,
    "Fake XP": 1930
  }
}
```

```py
from aiohttp import request

async def get_user(user_id):
  async with request("GET", f"/leveling/users/user/{user_id}") as resp:
    data = await resp.json()
    return data
```

#### /leveling/users/leaderboard

```json
{
  "Guild ID": 12345,
  "leaderboard": [
    {
      "12345": 20487
    }
  ]
}
```

```py
from aiohttp import request

async def get_leaderboard(guild_id):
  async with request("GET", f"/leveling/users/leaderboard/{guild_id}") as resp:
    #limit defaults to 10
    data = await resp.json()
    return data
```

### /leveling/users/leaderboard

```json
{
 "leaderboard": [
   {
     "12345": 18557
   }
  ]
}
```

```py
from aiohttp import request

async def get_leaderboard(guild_id):
  async with request("GET", f"/leveling/users/leaderboard?limit=50") as resp:
    #limit of the limit is 50
    data = await resp.json()
    return data
```

### /economy/users/user

```json
{
 "user": {
  "User ID": 12345,
  "Coins":  18557,
  "Jail": false,
  "Guard": false,
  "items": [
   {
   }
  ]
 }
}
```

```py
from aiohttp import request

async def get_user(user_id):
  async with request("GET", f"/economy/users/user/{user_id}") as resp:
    data = await resp.json()
    return data
```

### /economy/users/leaderboard

```json
{
 "leaderboard": [
  {
   "12345": 18557
  }
 ]
}
```

```py
from aiohttp import request

async def get_leaderboard():
  async with request("GET", f"/economy/users/leaderboard?limit=1") as resp:
    #user with the most coins
    data = await resp.json()
    return data
```
