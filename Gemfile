source "https://rubygems.org"
# Run with
#   bundle exec jekyll serve (--port 4001)
#
# gem "jekyll", "~> 4.0.0"
# THEME SELECT
# gem "minima", "~> 2.5"
gem "just-the-docs"
# we use GitHub Pages, so I removed the "gem "jekyll" above
# To upgrade, run `bundle update github-pages`
gem "github-pages", "~> 204", group: :jekyll_plugins
# PLUGINS
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-sitemap"
  gem "jekyll-relative-links"
  gem "jekyll-remote-theme"
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1.1", :install_if => Gem.win_platform?

