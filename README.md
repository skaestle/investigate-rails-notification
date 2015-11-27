== README

This app showcases an error with `ActiveSupport::Notification` where fanout dies out because of missing initialization of `Thread.current[:_timestack]]`

To see it in action:

* `bundle install`
* `rake db:create`
* `rake db:migrate`
* `rails server`

now visit `localhosts:3000/posts`. the first visit will result in:

`undefined method `pop' for nil:NilClass` thrown in `activesupport (4.2.5) lib/active_support/notifications/fanout.rb:126:in `finish'`

the second visit to the page will work.
