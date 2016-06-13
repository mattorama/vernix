# setup_jekyll

basic jekyll setup on github pages

* install latest version of ruby without need for sudo
brew install ruby
* restart terminal to ensure path reflects new version of ruby

* install bundler and the github pages gem
```
gem install bundler
gem install github-pages
```

* create a new jekyll project
```
jekyll new setup_jekyll
cd ./setup_jekyll
```

* add the Gemfile to the jekyll project
```
echo "source 'https://rubygems.org'" > Gemfile
echo "gem 'github-pages', group: :jekyll_plugins" >> Gemfile
```

* install dependencies and update the github pages gem
```
bundle install
bundle update github-pages
```

* serve the project
```
bundle exec jekyll serve
```

* preview the project at http://localhost:4000

* create an empty repo on GitHub

* point the jekyll project to GitHub
```
echo "# setup_jekyll" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:mattorama/setup_jekyll.git
git push -u origin master
```

* modify _config.yml for serving as a project page on github
```
baseurl: "/setup_jekyll" # the subpath of your site, e.g. /blog
url: "http://mattorama.github.io" # the base hostname & protocol for your site
```

* serve and preview the site at http://localhost:4000/setup_jekyll/

* commit changes and push to gh-pages branch
```
git commit -am "fix url settings for github"
git push origin master
