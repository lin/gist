Local computer (i.e. Mac) setup for unicorn

```
gem 'unicorn' # add it to Gemfile
```

```
bundle install
```

make `pids` folder at `[root]/pids`
make `unicorn.pid` file under `[root]/pids/` directory

create a file as `config/unicorn.rb`, as in file 08 on this page.

create a file as `config/unicorn_init.sh`, as in file 09 on this page.