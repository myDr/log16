# Log16

Structured + Contextual JSON Logger wrapper

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'log16'
```

## Usage

```ruby
logger = Log16.new(Logger.new(STDOUT))
logger.info("hello", name: "bob") # => {"name":"bob","lvl":"info","msg":"hello","t":"2015-03-18T15:52:45+11:00"}
context = logger.new_context(name: "bob")
context.notice("hi") # => {"name":"bob","lvl":"notice","msg":"hi","t":"2015-03-18T15:52:45+11:00"}
context.level = Logger::WARN # Affects the parent logger level too as they share the object
context.debug("invisible") # => no output
```

## Contributing

1. Fork it ( https://github.com/[my-github-username]/log16/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
