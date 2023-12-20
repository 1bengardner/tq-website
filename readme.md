# TQ Website

<img src="https://github.com/1bengardner/tq-website/assets/6226898/a7c30871-19a7-4eaa-b18a-f2c15e2d7894" alt="Landing page" width="270" />
<img src="https://github.com/1bengardner/tq-website/assets/6226898/f55a561b-4fcf-4a19-b262-f14d74ca0b2e" alt="Compendium: main page" width="270" />
<img src="https://github.com/1bengardner/tq-website/assets/6226898/467176a3-56f3-4567-9d9f-447b4c2a5466" alt="Compendium: detail page" width="270" />

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
