source "https://rubygems.org"

ruby_version = Gem::Version.new(RUBY_VERSION.dup)

group :test, optional: true do
  gem 'rake', ruby_version <= Gem::Version.new('1.9.3') ? '~> 11.3.0' : '~> 12.3.0'
  gem 'rspec'
  gem 'rspec-mocks'
  gem 'rdoc', ruby_version < Gem::Version.new('2.2.0') ? '4.3.0' : '~> 5.1.0'
  gem 'pry'
  gem 'addressable', '~> 2.3.8'
  if ruby_version >= Gem::Version.new('2.2.2')
    gem 'delayed_job', ruby_version < Gem::Version.new('2.5.0') ? '4.1.7': '>4.1.7'
    gem 'i18n', ruby_version <= Gem::Version.new('2.3.0') ? '1.4.0' : '>1.4.0'
  end
  gem 'webmock', ruby_version <= Gem::Version.new('1.9.3') ? '2.3.2': '>2.3.2'
  gem 'hashdiff', ruby_version <= Gem::Version.new('1.9.3') ? '0.3.8': '>0.3.8'
  if ruby_version >= Gem::Version.new('2.7.0')
    gem 'did_you_mean', '~> 1.4.0'
  elsif ruby_version >= Gem::Version.new('2.5.0')
    gem 'did_you_mean', '~> 1.3.1'
  elsif ruby_version >= Gem::Version.new('2.4.0')
    gem 'did_you_mean', '~> 1.1.0'
  elsif ruby_version >= Gem::Version.new('2.3.0')
    gem 'did_you_mean', '~> 1.0.4'
  end
end

group :coverage, optional: true do
  gem 'simplecov'
  gem 'coveralls'
end

group :rubocop, optional: true do
  gem 'rubocop', '~> 0.83'
end

group :sidekiq, optional: true do
  gem 'sidekiq', '~> 5.2.7'
  # redis 4.1.2 dropped support for Ruby 2.2
  gem 'redis', ruby_version < Gem::Version.new('2.3.0') ? '4.1.1' : '>= 4.1.2'
end

group :doc, optional: true do
  gem 'hanna-nouveau'
end

gemspec
