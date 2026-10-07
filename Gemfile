source "https://rubygems.org"

# Run Jekyll with `bundle exec`, like so:
#
#     bundle exec jekyll serve
#
# Le site est construit et déployé sur GitHub Pages par la GitHub Action
# .github/workflows/pages.yml (et non plus par le build "classique" de GitHub Pages).
gem "jekyll", "~> 4.4"
gem "just-the-docs", "0.10.1"

group :jekyll_plugins do
  gem "jekyll-include-cache"
  gem "jekyll-redirect-from"
  gem "jekyll-relative-links"
  gem "jekyll-seo-tag"
  gem "jekyll-titles-from-headings"
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", :platforms => [:mingw, :x64_mingw, :mswin]

gem "webrick"
