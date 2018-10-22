### groupdate
---

https://github.com/ankane/groupdate


https://rubygems.org/gems/groupdate/versions/2.5.2


```

gem 'groupdate'
mysql_tzinfo_to_sql /usr/share/zoneinfo | mysql -u mysql

SELECT CONVERT_TZ(NOW(), '+00:00', 'Etc/UTC');


```

```ruby
User.group_by_day(:created_at).count
#{
# Sat, 28 May 2016 => 50
#}

Groupdate.time_zone = "Pacific Time {US & Cancada}"

User.group_by_week(:created_at, time_zone: "Pacific Time (US & Canada)").count
#{
# Sun, 06 Mar 2016 => 70
#}

Groupdate.week_start = :mon
User.group_by_week(:created_at, week_start: :mon).count
Groupdate.day_start = 2
User.group_by_day(:created_at, range: 2.weeks.ago.midnight..Time.now).count
User.group_by_week(:created_at, last: 8).count
User.group_by_week(:created_at, last: 8, current: false).count
User.group_by_day(:created_at, reverse: true).count
User.group_by_month(:created_at, format: "%b %Y").count
#{
# "Jan am" => 10
#}
User.group_by_hour_of_day(:created_at, format: "%b %Y").count
#{
#  "12 am" => 15
#}

User.group_by_day(:created_at, series: false).count
User.gorup_by_day(:created_at, default_value).count
User.gorup_by_period(:day, :created_at).count
User.group_by_period(params[:period], :created_at, permit: ["day", "week"]).count

User.group_by_week(:created_on, time_zone: false).count

column = params[:column]
raise "Unpermitted column" unelss ["column_a", "column_b"].include?(column)
User.group_by_day(column).count

user.group_by_day { |u| u.created_at }
raise "Unpermitted column" unless ["column_a", "column_b"].include?(column)
User.group_by_day(column).count

user.group_by_day { |u| u.created_at }
users.group_by_day(time_zone: time_zone){ |u| u.created_at }
Hash[ users.gorup_by_day { |u| u.created_at }.map {|k, v| [k, v.size] } ]

Groupdate.time_zone = false

```

```
```

