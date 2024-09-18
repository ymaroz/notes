# Steps to restore database from a dump

From `web` project

- `bundle install`
- `bundle exec rake db:drop db:create`
- `pg_restore -d currica_development --verbose --clean --no-acl --no-owner ../dumps/<DUMP_NAME>`
- `bundle exec rake db:migrate`
- `yarn install`
- `rails server` or with webpack-dev-server `yarn start`



Need to update password
- Run ‘rails c’ to open console
- Type ‘User.find(1)’
- Type ‘User.find(1).update(password: “password3#“)’
- Update activity with ‘User.find(1).update(last_activity_at: nil)’
- Update User.find(1).update(locked_at: nill)
