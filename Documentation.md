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
Method | Endpoint | Arguments | Additional query
-------|----------|-----------|------------
GET | /leveling/users/user | guild_id: int - user_id: int | None
GET | /leveling/users/leaderboard | guild_id: int | limit, reversed
GET | /leveling/users/leaderboard | None | limit, reversed
GET | /economy/users/user | user_id: int | None
GET | /economy/users/leaderboard | None | limit, reversed
GET | /social/badges | user_id: int | None
