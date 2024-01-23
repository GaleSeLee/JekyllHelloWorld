# JekyllHelloWorld
This repo is following the [tutorial](https://huangshuo.net/2022/jekyll-tutorials/index.html) 

## Install ruby and Jekyll
### Ubuntu
```
sudo apt update 
sudo apt upgrade
sudo apt install ruby-full build-essential
gem install jekyll bundler(if you don't want to install Gem to /usr/bin, please export GEM_HOME)
```
### Macos
```
install homebrew
brew install chruby ruby-install
ruby-install ruby-3.3.0(if an error incurs, brew install wget and brew upgrade wget may be helpful)
echo "source ${HOMEBREW_PREFIX}/opt/chruby/share/chruby/chruby.sh" >> env.sh
ehco "source ${HOMEBREW_PREFIX}/opt/chruby/share/chruby/auto.sh" >> env.sh
echo "chruby ruby-3.3.0" >> env.sh
source env.sh
gem install jekyll bundler
```

## How to run
```
bundle exec jekyll build
bundle exec jekyll serve
```


## File Tree
```
.
├── assets
│   └── css
│       └── style.scss
├── _authors
│   └── zeyuli.md
├── blog.html
├── _config.yml
├── _data
│   └── navigation.yml
├── Gemfile
├── Gemfile.lock
├── _includes
│   ├── about.md
│   └── navigation.html
├── index.html
├── _layouts
│   ├── author.html
│   ├── default.html
│   └── post.html
├── _post
│   └── 2022-01-01-welcome.md
├── README.md
├── _sass
│   └── main.scss
├── _site
│   ├── assets
│   │   └── css
│   │       ├── style.css
│   │       └── style.css.map
│   ├── authors
│   │   └── zeyuli.html
│   ├── blog.html
│   ├── index.html
│   ├── README.md
│   └── staff.html
└── staff.html
```

### [Liquid](https://shopify.github.io/liquid)
Three component: objects, tags and filters
#### Tags
1. Control flow: if, for
2. include: {% include "template-name" %}
3. Variable: assign, increment, decrease
#### Filters
1. Pre-defined specific functions



### File Description
#### Gemfile
`bundle install` will install gem according the Gemfile. And Gemfile will copy as the Gemfile.lock.

#### _site
After exec `bundle exec jekyll build`, the jekyll will create `_site` folder and generate all the static files into `_site`.

#### index.html blog.html and staff.html
1. Front Matte, configuration between two `---`.(As seen as the page-level variables).
2. layout will use the html in `_layouts`, e.g. layout: default will use _layouts/default.html. {{content}} is a pre-defined variable to pass the body from index.html(caller) into layout/*html(callee)