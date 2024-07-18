# Major League Baseball (MLB) API

The **Major League Baseball (MLB) API** offers comprehensive access to real-time and historical data from the world of MLB. Designed for developers, analysts, and baseball enthusiasts, this API provides detailed statistics, game information, player data, and more, allowing for deep insights and integration into applications. This API can be located on [RapidAPI](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/major-league-baseball-mlb)

## Key Features

- **Live Game Data**: Access real-time updates during MLB games, including scores, plays, and player stats.
- **Player and Team Information**: Retrieve detailed profiles and statistics for players and teams, including standings and performance metrics.
- **Game Schedule**: Get information on upcoming games, including dates, locations, and matchups.
- **Historical Data**: Access past game results, player statistics, and historical records for in-depth analysis.

## Getting Started

1. **Sign Up**: Create an account on RapidAPI.
2. **Subscribe**: Choose a subscription plan suitable for your needs.
3. **API Key**: Obtain your unique API key to begin making requests.
4. **Documentation**: For detailed usage instructions, visit the [MLB API Documentation](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/major-league-baseball-mlb).


## Endpoint: Retrieve Play by Play Data

### Description
This endpoint allows users to retrieve play-by-play data for a specific game using its unique game ID.

### HTTP Request
**GET** `/pbp/:gameId`

### URL Parameters
- `gameId` (required): A unique identifier for the game. Example: `401472105`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the play-by-play data for the specified game.

#### Error
- **Code**: `400 Bad Request`
  - **Content**: `{ "error": "Please enter the gameId" }`
  - **Description**: Returned when the `gameId` parameter is missing.
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/pbp/401472105"
```

## Endpoint: Retrieve Box Score Data

### Description
This endpoint allows users to retrieve the box score data for a specific game using its unique game ID.

### HTTP Request
**GET** `/boxscore/:gameId`

### URL Parameters
- `gameId` (required): A unique identifier for the game. Example: `401472105`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the box score data for the specified game.

#### Error
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/boxscore/401472105"
```


## Endpoint: Retrieve Summary Data

### Description
This endpoint allows users to retrieve the summary data for a specific game using its unique game ID.

### HTTP Request
**GET** `/summary/:gameId`

### URL Parameters
- `gameId` (required): A unique identifier for the game. Example: `401472105`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the summary data for the specified game.

#### Error
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/summary/401472105"
```

## Endpoint: Retrieve Picks Data

### Description
This endpoint allows users to retrieve picks data for a specific game using its unique game ID.

### HTTP Request
**GET** `/picks/:gameId`

### URL Parameters
- `gameId` (required): A unique identifier for the game.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the picks data for the specified game.

#### Error
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/picks/401472105"
```

## Endpoint: Retrieve Schedule Data

### Description
This endpoint allows users to retrieve the schedule data for a specific date and group.

### HTTP Request
**GET** `/schedule`

### Query Parameters
- `year` (required): The year of the schedule. Example: `2021`.
- `month` (required): The month of the schedule. Example: `02`.
- `day` (required): The day of the schedule. Example: `15`.
- `group` (optional): The group identifier. Default is `50`.
- `seasontype` (optional): The season type. Default is `2`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the schedule data for the specified date and group.

#### Error
- **Code**: `400 Bad Request`
  - **Content**: `{ "error": "Please enter the year, month, and day" }`
  - **Description**: Returned when the `year`, `month`, or `day` parameters are missing.
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "Something went wrong: Please try again later or change the parameters!" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/schedule?year=2021&month=02&day=15"
```


## Endpoint: Retrieve Scoreboard Data

### Description
This endpoint allows users to retrieve the scoreboard data for a specific date.

### HTTP Request
**GET** `/scoreboard`

### Query Parameters
- `year` (required): The year of the scoreboard data. Example: `2021`.
- `month` (required): The month of the scoreboard data. Example: `02`.
- `day` (required): The day of the scoreboard data. Example: `15`.
- `limit` (optional): The limit on the number of results. Default is `200`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the scoreboard data for the specified date.

#### Error
- **Code**: `400 Bad Request`
  - **Content**: `{ "error": "Please enter the year, month, and day" }`
  - **Description**: Returned when the `year`, `month`, or `day` parameters are missing.
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/scoreboard?year=2021&month=02&
```



## Endpoint: Retrieve Standings Data

### Description
This endpoint allows users to retrieve the standings data for a specific year and group.

### HTTP Request
**GET** `/standings`

### Query Parameters
- `year` (required): The year of the standings data. Example: `2021`.
- `group` (optional): The group type, either `league` or `conference`. Default is `league`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the standings data for the specified year and group.

#### Error
- **Code**: `400 Bad Request`
  - **Content**: `{ "error": "Please enter the year" }`
  - **Description**: Returned when the `year` parameter is missing.
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/standings?year=2021&group=league"
```

## Endpoint: Retrieve Team List Data

### Description
This endpoint allows users to retrieve a list of teams.

### HTTP Request
**GET** `/team-list`

### Query Parameters
- `limit` (optional): The limit on the number of results. Default is `500`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the list of teams.

#### Error
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/team-list?limit=500"
```



## Endpoint: Retrieve Team Info Data

### Description
This endpoint allows users to retrieve information about a specific team using its unique team ID.

### HTTP Request
**GET** `/team-info/:teamId`

### URL Parameters
- `teamId` (required): A unique identifier for the team. Example: `52`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the information about the specified team.

#### Error
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/team-info/52"
```




## Endpoint: Retrieve Team Players Data

### Description
This endpoint allows users to retrieve a list of players for a specific team using its unique team ID.

### HTTP Request
**GET** `/team-players/:teamId`

### URL Parameters
- `teamId` (required): A unique identifier for the team. Example: `52`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the list of players for the specified team.

#### Error
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/team-players/52"
```




## Endpoint: Retrieve News Data

### Description
This endpoint allows users to retrieve news data.

### HTTP Request
**GET** `/news`

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the news data.

#### Error
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "<error_message>" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/news"
```


## Endpoint: Retrieve Player Statistics

### Description
This endpoint allows users to retrieve statistics for a specific player using their player ID.

### HTTP Request
**GET** `/player-statistic`

### Query Parameters
- `playerId` (required): The unique identifier for the player. Example: `42403`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the statistics for the specified player.

#### Error
- **Code**: `400 Bad Request`
  - **Content**: `{ "error": "Please enter the PlayerId" }`
  - **Description**: Returned when the `playerId` parameter is missing.
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "Internal Server Error" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/player-statistic?playerId=42403"
```



## Endpoint: Retrieve Team Statistics

### Description
This endpoint allows users to retrieve statistics for a specific team using its team ID.

### HTTP Request
**GET** `/team-statistic`

### Query Parameters
- `teamId` (required): The unique identifier for the team. Example: `12`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the statistics for the specified team.

#### Error
- **Code**: `400 Bad Request`
  - **Content**: `{ "error": "Please enter the teamId" }`
  - **Description**: Returned when the `teamId` parameter is missing.
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "Internal Server Error" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/team-statistic?teamId=12"
```




## Endpoint: Retrieve Injuries for the Current Season

### Description
This endpoint allows users to retrieve information about injuries for the current season.

### HTTP Request
**GET** `/injuries`

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the injuries data for the current season.

#### Error
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "Internal Server Error" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/injuries"
```



## Endpoint: Retrieve Team Roster

### Description
This endpoint allows users to retrieve the roster for a specific team in a given season.

### HTTP Request
**GET** `/team-roster`

### Query Parameters
- `teamId` (required): The unique identifier for the team. Example: `16`.
- `season` (required): The season for which the roster is requested. Example: `2023`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the roster for the specified team and season.

#### Error
- **Code**: `400 Bad Request`
  - **Content**: `{ "error": "Please enter the teamId and the season" }`
  - **Description**: Returned when the `teamId` or `season` parameters are missing.
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "Internal Server Error" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/team-roster?teamId=16&season=2023"
```



## Endpoint: Retrieve MLB Schedules by Team

### Description
This endpoint allows users to retrieve the schedules for MLB games by team and season.

### HTTP Request
**GET** `/schedule-team`

### Query Parameters
- `teamId` (required): The unique identifier for the team. Example: `16`.
- `season` (optional): The season for which the schedule is requested. Default is `2023`.

### Responses

#### Success
- **Code**: `200 OK`
- **Content**: JSON object containing the schedule for MLB games for the specified team and season.

#### Error
- **Code**: `400 Bad Request`
  - **Content**: `{ "error": "Please enter the teamId and the season" }`
  - **Description**: Returned when the `teamId` or `season` parameters are missing.
- **Code**: `500 Internal Server Error`
  - **Content**: `{ "error": "Internal Server Error" }`
  - **Description**: Returned when there is an error processing the request.

### Example Request
```bash
curl -X GET "https://api.example.com/schedule-team?teamId=16&season=2023"
```
## Commonly Asked Questions

### 1. What kind of data can I access through the MLB API?
You can access live game data, player and team statistics, game schedules, and historical data.

### 2. How do I authenticate my API requests?
You need to include your API key in the headers of your requests as specified in the API documentation.

### 3. Are there usage limits for the API?
Yes, usage limits depend on the subscription plan you choose. Check the RapidAPI dashboard for specifics.

### 4. Can I filter data by specific teams or players?
Yes, the API allows filtering to retrieve data for specific teams, players, or games.

### 5. Is historical data available for past seasons?
Yes, the MLB API includes comprehensive historical data, allowing for detailed statistical analysis and comparisons.

For more information and to start using the MLB API, visit [MLB API on RapidAPI](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/major-league-baseball-mlb).
