
# SpreadshirtClient

Use this gem to communicate with the spreadshirt API.
http://developer.spreadshirt.net

## Installation

Add this line to your application's Gemfile:

```
gem 'spreadshirt_client'
```

And then execute:

```
$ bundle
```

Alternatively, you can of course install it without bundler via:

```
$ gem install spreadshirt_client
```

## Setup

First, you need to setup your API credentials:

```ruby
SpreadshirtClient.api_key = "..."
SpreadshirtClient.api_secret = "..."
SpreadshirtClient.base_url = "http://api.spreadshirt.net/api/v1" # optional
SpreadshirtClient.timeout = 5 # optional (default: 30)
```

## Usage

The DSL to interact with the spreadshirt API is similar
to RestClient's DSL.

```ruby
# Add an article to a previously created spreadshirt basket.
SpreadshirtClient.post "/baskets/[basket_id]/items", "<basketItem>...</basketItem>", :authorization => true

# To make a request that requires a valid spreadshirt session.
SpreadshirtClient.post "/orders", "<order>...</order>", :authorization => true, :session => "..."

# Update a line item.
SpreadshirtClient.put "/baskets/[basket_id]/items/[item_id]", "<basketItem>...</basketItem>", :authorization => true

# Retrieve the checkout url for a spreadshirt basket.
SpreadshirtClient.get "/baskets/[basket_id]/checkout", :authorization => true

# Retrieve a spreadshirt shop's articles.
SpreadshirtClient.get "/shops/[shop_id]/articles", :params => { :limit => 50 }

...
```

Please take a look into the spreadshirt API docs for more details.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

