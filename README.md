# InstaScraper

Scrapes Instagram

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'insta_scraper'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install insta_scraper

## Usage

Subclasses of InstaScraper::HTML are scraping html endpoints.
Subclasses of InstaScraper::JSON are scraping json endpoints.

* InstaScraper::HTML::Account

```ruby
account = InstaScraper::HTML::Account.new('barna.kovacs.codes')

account.json #=> #<Hashie::Mash...
account.json.deep_find('followed_by').fetch('count') #=> 4
```

* InstaScraper::HTML::Media

```ruby
media = InstaScraper::HTML::Media.new('BGFVAPPIaBQ')

media.json #=> #<Hashie::Mash...
media.json.deep_find('comments').fetch('count') #=> 1892
```

* InstaScraper::JSON::AccountMedia

```ruby
account_media = InstaScraper::JSON::AccountMedia.new('barna.kovacs.codes')

account_media.json #=> #<Hashie::Mash...
account_media.json.fetch('items') #=> [...]
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/preciz/insta_scraper.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

