# Twitter::Bootstrap::Rails::Confirm

This gem adds some javascript to change the default behaviour of data-confirm processing.

The normal confirm dialog shows a text with buttons 'ok' and 'cancel'. More information is needed here for a user to make the right decision. This gem therefore also adds:

* data-confirm-title (default: window.top.location.origin)
* data-confirm-cancel (default: 'cancel')
* data-confirm-proceed (default: 'ok')
* data-confirm-proceed-class (default: 'brn-primary')

## Installation

Add this line to your application's Gemfile:

    gem 'twitter-bootstrap-rails-confirm'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install twitter-bootstrap-rails-confirm

## Usage

There is nothing you need to do to get this working. A helper could be useful for handling large amount of destroy buttons:

    def destroy_link_to(path, options)
      link_to t('.destroy'), path, 
        :method => :delete,
        :class => "btn",
        :confirm => t('.destroy_confirm.body', :item => options[:item]),
        "data-confirm-title" => t('.destroy_confirm.title', :item => options[:item]),
        "data-confirm-cancel" => t('.destroy_confirm.cancel', :item => options[:item]),
        "data-confirm-proceed" => t('.destroy_confirm.proceed', :item => options[:item]),
        "data-confirm-proceed-class" => "btn-danger"
    end

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
