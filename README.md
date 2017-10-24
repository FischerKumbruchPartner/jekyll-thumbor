# Jekyll::ThumborTag

A [Jekyll](https://jekyllrb.com/) template tag for [Thumbor](https://github.com/thumbor/thumbor) imaging service.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'jekyll-thumbor', :git => 'https://github.com/FischerKumbruchPartner/jekyll-thumbor.git'
```

And then execute:

```
$ bundle
```

You now need to enable the plugin in your Jekyll web site. Append it to the `gems` array in your `_config.yml` file:

```yaml
plugins:
  - jekyll-thumbor
```

## Usage
You need to add an array for thumbor configuration to your `_config.yml` file:

```yaml
thumbor:
  url: "https://your-thumbor-server"
  key: "your-key"
  active_environments: ["development", "production"]
```
**Do not add a slash at the end of your url**


```html
<img src="{% thumbor_tag https://example.org/picture.jpg, width: 500, height: 500 %}">


<img src="{% thumbor_tag {{ page.background_img | absolute_url}}, width: 500, height: 500 %}">
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, run `bumpversion minor`, and then run `bundle exec rake release` to create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
