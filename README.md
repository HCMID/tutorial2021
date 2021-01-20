# Tutorial materials for HC MID

This repository hosts the source material for the jekyll web site at <https://hcmid.github.io/tutorial2021/>.

You should develop and test web pages in the `src` directory.  Within the source directory, you can start a local web server with `bundle exec jekyll serve`.  (Since jekyll is written in ruby, you will need to have [the ruby language](https://www.ruby-lang.org/en/documentation/installation) installed on your computer, and will need to have installed the bundler gem:  `gem install bundler`.)

Github pages serves the website from the `docs` directory.  You can update or publish pages by copying them from `src` to `docs`.  (Do *not* copy `_config.yml` or `Gemfile` from the `src` directory:  these files configure how jekyll runs locally on your computer.)
