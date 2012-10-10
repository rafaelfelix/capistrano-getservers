# Capistrano::Getservers

capistrano-getservers makes it easier for you to deploy to your EC2
instances.  By supplying a Hash to the `get_servers` method,
capistrano-getservers connects to EC2 and retrieves all instances with
matching tags.


## Installation

Add this line to your application's Gemfile:

    gem 'capistrano-getservers'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install capistrano-getservers

## Usage


In your capistrano script:
```ruby
  `get_servers({'app' => 'app_name', 'cluster' => 'cluster',
'environment' => 'environment' ... }`
```

Additionally, you can use the `parse_tags` function to create your Hash
via the command line as follows:

In your capistrano script:
```ruby
set :tags, ENV['TAGS'] || {}
cli_tags = parse(tags)
get_servers(cli_tags)
```

cap staging deploy TAGS=key1:value1,key2:value2,key3:value3...


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
