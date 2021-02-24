# frozen_string_literal: true

# Run Jekyll with `bundle exec`:
# bundle exec jekyll serve
# bundle exec jekyll serve --livereload

source "https://rubygems.org"

git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }

# gem "rails"

# gem "jekyll", "~> 4.2"
# To use Github Pages, remove the "gem "jekyll"" above and 
# uncomment the line below. To upgrade, run `bundle update github-pages`
gem "github-pages", group: :jekyll_plugins
# If you have any plugins, put them here!
group :jekyll_plugins do
    gem "jekyll-feed", "~> 0.12"
end

gem 'wdm', '>= 0.1.1', :install_if => Gem.win_platform?

gem 'eventmachine', '1.2.7', git: 'https://github.com/eventmachine/eventmachine.git', tag: 'v1.2.7'

