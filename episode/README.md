# Episode queries

This folder contains example GraphQL queries to fetch episodes from the Rick and Morty GraphQL API.

Endpoint: https://rickandmortyapi.com/graphql

Files:

- `episode-page-1.graphql` - query for `episode(id: 1)` requesting `id`, `name`, `air_date`, and `episode`.
- `episode-id-1-output.json` - sample response for episode id 1.
Additional paginated character queries and sample outputs are included in this folder as examples for related exercises.

Files added for characters pagination:

- `characters-page-1.graphql` — query for page 1
- `characters-page-1-output.json` — sample response (subset of results)
- `characters-page-2.graphql` — query for page 2
- `characters-page-2-output.json` — sample response (subset of results)
- `characters-page-3.graphql` — query for page 3
- `characters-page-3-output.json` — sample response (subset of results)
- `characters-page-4.graphql` — query for page 4
- `characters-page-4-output.json` — sample response (subset of results)

Run example (PowerShell):

```
Invoke-RestMethod -Uri 'https://rickandmortyapi.com/graphql' -Method Post -Body (@{query='query { episode(id:1) { id name air_date episode } }'} | ConvertTo-Json) -ContentType 'application/json'
```

PowerShell example to fetch characters page 1:

```
Invoke-RestMethod -Uri 'https://rickandmortyapi.com/graphql' -Method Post -Body (@{query='query { characters(page:1) { info { count pages } results { id name status image } } }'} | ConvertTo-Json) -ContentType 'application/json'
```

Or with curl:

```
curl -s -X POST https://rickandmortyapi.com/graphql -H "Content-Type: application/json" -d "{\"query\":\"query { characters(page:1) { info { count pages } results { id name status image } } }\"}"
```