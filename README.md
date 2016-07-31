[![](https://images.microbadger.com/badges/image/danjellz/docker-jekyll.svg)](http://microbadger.com/#/images/danjellz/docker-jekyll "Get your own image badge on microbadger.com") [![GitHub issues](https://img.shields.io/github/issues/danjellesma/docker-jekyll.svg)](https://github.com/danjellesma/docker-jekyll/issues) [![GitHub stars](https://img.shields.io/github/stars/danjellesma/docker-jekyll.svg)](https://github.com/danjellesma/docker-jekyll/stargazers) [![GitHub forks](https://img.shields.io/github/forks/danjellesma/docker-jekyll.svg)](https://github.com/danjellesma/docker-jekyll/network) [![CircleCI](https://circleci.com/gh/danjellesma/docker-jekyll/tree/master.svg?style=svg)](https://circleci.com/gh/danjellesma/docker-jekyll/tree/master) [![](https://images.microbadger.com/badges/version/danjellz/docker-jekyll.svg)](http://microbadger.com/#/images/danjellz/docker-jekyll "Get your own version badge on microbadger.com")

# Simple, Lightweight Docker-Jekyll Image
This is the source for a lightweight Docker image for the Jekyll blog system.

It was inspired by [grahamc's image](https://github.com/grahamc/docker-jekyll) which can be found here.

## Why use this image?
The differentiator between the two images is the base image they are built from. Grahamc's is based on Ubuntu and this is based on Alpine Linux.

Image        | Base image      | Size
------------- |:-------------: |:-------------:      
`grahamc/jekyll`      | Ubuntu        | `807 MB`
`danjellz/jekyll`    | Alpine      |    `354 MB`

That is a difference of `454 MB` -- 56% smaller!

## Functionality

If you were using Grahamc's image you should be able to use this as a drop in replacement. It has all the same gems installed.

Use example:

```
sudo docker run --rm -v "$PWD:/src" danjellz/jekyll build
```

or for repeated calls:

```
alias jekyll='sudo docker run --rm -v "$PWD:/src" -p 4000:4000 grahamc/jekyll'
jekyll build
jekyll serve -H 0.0.0.0
```

run as a background daemon:
```
sudo docker run -d -v "$PWD:/src" -p 4000:4000 danjellz/jekyll serve -H 0.0.0.0
```

## Goodies
 - Supports pygments syntax highlighting
 - Supports Github Pages
 - Supports Jekyll Redirect From
 - Supports Kramdown
 - Supports RDiscount
 - Supports Rouge


# License: Public Domain
