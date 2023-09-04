# Fantasy Premier League API

## Installation

### Npm
```shell
npm install fantasypl
```

### Yarn
```shell
yarn add fantasypl
```

### Pnpm
```shell
pnpm add fantasypl
```

## Usage

A basic example to fetch all data from the [core endpoint]("https://fantasy.premierleague.com/api/bootstrap-static/"). The returned `data` is a typed object of type `Bootstrap`.

```ts
import { fetchBootstrap } from "fantasypl"

const fetchData = async () => {
  const data = await fetchBootstrap()

  return data;
}

fetchData()
```

## Notes

Forked from [jeppe-smith/fpl-api](https://github.com/jeppe-smith/fpl-api). Most of the implementation remains the same but I will be updating the package for my requirements.
