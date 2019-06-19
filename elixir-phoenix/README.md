# Phoenix (Elixir)

This CircleCI config is for Elixir Phoenix apps using PostgreSQL database.

## Images

- `circleci/elixir:1.7.3`
- `circleci/postgres:9.6`

## Caveats

- The projects must have the testing database configured in the following way:

```elixir
config :my_app, MyApp.Repo,
  username: "devuser",
  password: "devuser",
  database: "test_database",
  hostname: "localhost",
  pool: Ecto.Adapters.SQL.Sandbox
```
