source "https://rubygems.org"

# GitHub Pages 빌드 환경과 버전을 맞춥니다.
gem "github-pages", group: :jekyll_plugins

group :jekyll_plugins do
  gem "jekyll-sitemap"
  gem "jekyll-feed"
end

# Windows / JRuby
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end
gem "wdm", "~> 0.1", platforms: [:mingw, :x64_mingw, :mswin]
