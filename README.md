# FacebookChat

FacebookChat is a gem which send a chat message to any facebook friends using Facebook Chat API. It makes you to handle a facebook chat message more easy. If you'd like to know about Facebook Chat API, please check [Facebook Developer's page](https://developers.facebook.com/docs/chat/).

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'facebook_chat'
```

And then execute:

```console
$ bundle install
```

Or install it yourself as:

```console
$ gem install facebook_chat
```

## Usage

### Configure

First, you have to configure to Facebook Chat API Client.

If you are developing on Rails, you might want to place following code to `config/initializers/facebook_chat.rb`.

```ruby
require 'facebook_chat'

FacebookChat::Client.configure do |config|
  config.api_key = '****' # your facebook application's api key
  config.host = 'chat.facebook.com' # you can omit this line. Default host value is 'chat.facebook.com'
end
```

And then, create `FacebookChat::Client` instance and call `send` method.

```ruby
access_token = '****' # message sender's facebook access token
cilent = FacebookChat::Client.new(access_token)

to = '1000000000' # facebook user id you want to send a message
client(to, "hey, what's up?")
```

you can notice that a message is sent to the user who have id `1000000000`.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
