# FPL API

Use the public endpoints from the official api from https://fantasy.premierleague.com. Return values are typed using Typescript and kept up to date as good as possible - some variance should be expected, but it is 95% accurate. Private endpoints that require a session are not implemented yet, but hopefully they will be soon.

This can be used in the browser and with node.js.

## Installation

`$ npm install fantasypl`

## Usage

`import FplApi from 'fantasypl'`

You can use fantasypl in the browser by using a module bundler like webpack, rollup, etc.

## Methods

### fetchBootstrap

General data such as players, teams, gameweeks, etc.

```
import { fetchBootstrap } from 'fantasypl'

const data = await fetchBootstrap()
```

### fetchElementSummary

Data for a player.

```
import { fetchElementSummary } from 'fantasypl'

const playerId = 1
const data = await fetchElementSummary(playerId)
```

### fetchEntryEvent

Entry event data (picks, transfers, etc.).

| param   | description      | type   | default | required |
| ------- | ---------------- | ------ | ------- | -------- |
| entryId | ID of an entry   | number | -       | true     |
| eventId | ID of a gameweek | number | -       | true     |

```
import { fetchEntryEvent } from 'fantasypl'

const entryId = 1
const eventId = 38
const data = await fetchEntryEvent(entryId, eventId)
```

### fetchEventStatus

Current event status.

```
import { fetchEventStatus } from 'fantasypl'

const data = await fetchEventStatus()
```

### fetchFixtures

All fixtures or fixtures in a specific gameweek.

| param   | description      | type   | default   | required |
| ------- | ---------------- | ------ | --------- | -------- |
| eventId | ID of a gameweek | number | undefined | false    |

```
import { fetchFixtures } from 'fantasypl'

const data = await fetchFixtures()
```

### fetchLive

Live data for a gameweek.

| param   | description      | type   | default | required |
| ------- | ---------------- | ------ | ------- | -------- |
| eventId | ID of a gameweek | number | -       | true     |

```
import { fetchLive } from 'fantasypl'

const eventId = 33
const data = await fetchLive(eventId)
```

### fetchEntryHistory

Entry transfers etc.

| param   | description         | type   | default | required |
| ------- | ------------------- | ------ | ------- | -------- |
| entryId | ID of an entry team | number | -       | true     |

```
import { fetchEntryHistory } from 'fantasypl'

const entryId = 1
const data = await fetchEntryHistory(entryId)
```

### fetchEntry

Get an entry.

| param   | description         | type   | default | required |
| ------- | ------------------- | ------ | ------- | -------- |
| entryId | ID of an entry team | number | -       | true     |

```
import { fetchEntry } from 'fantasypl'

const entryId = 1
const data = await fetchEntry(entryId)
```

### fetchH2HMatches

Get an entry's matches from a H2H league.

| param    | description         | type   | default | required |
| -------- | ------------------- | ------ | ------- | -------- |
| leagueId | ID of a H2H league  | number | -       | true     |
| entryId  | ID of an entry team | number | -       | true     |
| page     | Page number         | number | 1       | true     |

```
import { fetchH2HMatches } from 'fantasypl'

const leagueId = 1
const entryId = 1
const data = await fetchH2HMatches(leagueId, entryId)
```

### fetchH2HLeagueStandings

Get H2H league standings page.

| param                  | description                 | type   | default | required |
| ---------------------- | --------------------------- | ------ | ------- | -------- |
| leagueId               | ID of a H2H league          | number | -       | true     |
| options.pageStandings  | Page number for standings   | number | 1       | true     |
| options.pageNewEntries | Page number for new entries | number | 1       | true     |

```
import { fetchH2HLeagueStandings } from 'fantasypl'

const leagueId = 1
const data = await fetchH2HLeagueStandings(leagueId)
```

### fetchClassicLeague

Get H2H league standings page.

| param                  | description                 | type   | default | required |
| ---------------------- | --------------------------- | ------ | ------- | -------- |
| leagueId               | ID of a classic league      | number | -       | true     |
| options.pageStandings  | Page number for standings   | number | 1       | true     |
| options.pageNewEntries | Page number for new entries | number | 1       | true     |
| options.phase          | Phase to show               | number | 1       | true     |

```
import { fetchClassicLeague } from 'fantasypl'

const leagueId = 1
const data = await fetchClassicLeague(leagueId)
```
