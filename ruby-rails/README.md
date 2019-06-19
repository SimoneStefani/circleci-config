# Ruby on Rails

This CircleCI config is for Ruby on Rails apps using PostgreSQL database. It includes tools such as [Rubocop](https://github.com/rubocop-hq/rubocop) for static analysis and code formatting, [Brakeman](https://github.com/presidentbeef/brakeman) for security analysis, [RSpec](https://rspec.info/) for testing and [Bundle dependencies auditing](https://github.com/rubysec/bundler-audit).

## Images

- `circleci/ruby:2.5.3`
- `circleci/postgres:9.6`

## Caveats

- The Rails app should have a configuration for a CircleCI environment located in a file such as `config/environments/circleci.rb`. Such environment can be very similar to the Rails default test environment.
- The Rails app should have a DB configuration for the CircleCI environment above such as:

```yml
circleci:
  adapter: postgresql
  encoding: unicode
  host: localhost
  username: postgres
  password:
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  database: test_database_circleci
```
