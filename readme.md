# TQ Website

## What?

This site acts as a companion to the game [Toshe's Quest II](https://github.com/1bengardner/toshes-quest-ii).

It is live at [https://toshesquest.com/](https://toshesquest.com/).

On this site you will find

- News
- Resources to help you get started
- Help and tips for playing the game
- Detailed game data (item, skill and enemy information).

## How?

This [Jekyll](https://jekyllrb.com/) static site is generated using [game data files](https://github.com/1bengardner/toshes-quest-ii/tree/master/data) and [kramdown](https://kramdown.gettalong.org/index.html) content with [Liquid](https://shopify.github.io/liquid/) "template language".

Although [GitHub Pages](https://pages.github.com/) (the platform on which the site is hosted) supports Jekyll projects as a source, the generated output is in [a different repo](https://github.com/1bengardner/tq-website-publish).

## ...Why?

Jekyll has different themes, and supports the theme [Minima v2](https://github.com/jekyll/minima/releases/) out of the box. But since I am using [Minima v3](https://github.com/jekyll/minima/) with a [custom skin](https://github.com/jekyll/minima/blob/master/_sass/minima/skins/solarized.scss), it was easier to just host the *generated output* on GitHub Pages, rather than try to get things working together nicely. Maybe it's possible, but it's been easier to have a second repository just for hosting the generated content.