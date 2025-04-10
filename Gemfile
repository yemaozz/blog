source "https://rubygems.org"
# 你好！这是你管理用于运行的 Jekyll 版本的地方。
# 当你想使用不同的版本时，请在下面修改它，保存文件，然后运行 `bundle install`。使用 `bundle exec` 运行 Jekyll，如下所示：
#
#     bundle exec jekyll serve
#
# 这将有助于确保运行的是正确的 Jekyll 版本。
# 祝你使用 Jekyll 愉快！
gem "jekyll", "~> 4.4.1"
# 这是新 Jekyll 网站的默认主题。你可以将其更改为任何你喜欢的主题。
gem "minima", "~> 2.5"
# 如果你想使用 GitHub Pages，请删除上面的 "gem "jekyll"" 并取消注释下面的行。要升级，请运行 `bundle update github-pages`。
# gem "github-pages", group: :jekyll_plugins
# 如果你有任何插件，请将它们放在这里！
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
end

# Windows 和 JRuby 不包含时区信息文件，因此需要捆绑 tzinfo-data gem 和相关库。
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# 用于在 Windows 上监视目录的性能增强工具
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]

# 在 JRuby 构建中，将 `http_parser.rb` gem 锁定到 `v0.6.x`，因为该 gem 的较新版本没有 Java 版本。
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]
gem 'jekyll-seo-tag'
gem 'jekyll-admin', group: :jekyll_plugins