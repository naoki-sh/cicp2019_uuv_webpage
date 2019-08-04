# cicp2019_uuv_webpage

## environment setting
- download source
```
  $ git clone git@github.com:naoki-sh/cicp2019_uuv_webpage.git
```

- install rvenv
- Mac
```
  $ brew install rbenv ruby-build
  $ echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
  $ source ~/.bash_profile
```

- install ruby
```
  $ rbenv install 2.6.0-dev
```
- version setting
- for gloval setting
```
  $ rbenv global 2.6.0-dev
```
- for local setting
```
  $ cd /path/to/ws/cicp2019_uuv_webpage
  $ rbenv local 2.6.0-dev
```

- install bundler
```
  $ gem install bundler
```

- make Gemfile and add following sentence
```
  source "https://rubygems.org"
  gem 'github-pages', group: :jekyll_plugins
  gem "minimal-mistakes-jekyll"
```

- test in the local environment
  $ bundle install --path vendor/bundle
  $ bundle exec jekyll s

