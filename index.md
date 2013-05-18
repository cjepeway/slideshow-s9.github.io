---
layout: default
title: Welcome
---

# {{ page.title }}

<div class="toc" markdown="1">
Contents:

* [What's Slide Show (S9)?](#whatis)
* [Getting Started in 1-2-3 Easy Steps](#steps)
* [What's Textile? What's Markdown?](#textile)
* [What's S5? What's S6?](#s6)
* [What's FullerScreen?](#fullerscreen)
* [About, License - Questions? Comments?](#about)
</div>

## What's Slide Show (S9)?   {#whatis}

A Ruby gem that lets you create slide shows and author slides in plain text
using a wiki-style markup language that's easy-to-write and easy-to-read.
The Slide Show (S9) project also collects and welcomes themes
and ships "out-of-the-gem" with built-in support
for "loss-free" gradient vector graphics themes.

## Getting Started in 1-2-3 Easy Steps   {#steps}

* Step 1: Author your slides in plain text using a wiki-style markup language
* Step 2: Generate your slide show using the `slideshow` gem
* Step 3: Open up your slide show (web page) in your browser and hit the space bar to flip through your slides
* That's it. Showtime!


### Step 0: Install the `slideshow` gem

~~~
$ gem install slideshow
~~~

### Step 1: Author your slides in plain text using a wiki-style markup language

Slide Show lets you author your slides using a wiki-style markup language
that's easy-to-write and easy-to-read. Let's create some slides about best practices for web services
using REST [`rest.textile`](http://github.com/geraldb/slideshow/raw/master/samples/rest.textile):

~~~
h1. Web Services REST-Style: Universal Identifiers, Formats & Protocols

Agenda

* What's REST?
* Universal Identifiers, Formats & Protocols
* The Holy REST Trinity - Noun, Verbs, Types
* REST Design Principles 
* Architecture Astronaut REST Speak

h1. Representational State Transfer (REST) - Meaningless Acronym? Wordplay?

rest - n. - peace, ease, or refreshment resulting from the insight that the web works

No matter what vendors tell you - no need to "Light Up the Web" - relax - built on
an *open architecture using universal identifiers, formats & protocols and _evolving_
open standards* - no need to reinvent the wheel and sign-up for single-vendor offerings.

h3. Broad Definition

* Best Practices for Designing Web Services for a Unified Human and Programable Web

h3. Narrow Definition

* Alternative to BigCo Web Services (SOAP, WS-*) and RPC-Style Web Services (XML-RPC)
~~~

Or

~~~
Web Services REST-Style: Universal Identifiers, Formats & Protocols
===================================================================

Agenda

- What's REST?
- Universal Identifiers, Formats & Protocols
- The Holy REST Trinity - Noun, Verbs, Types
- REST Design Principles 
- Architecture Astronaut REST Speak

Representational State Transfer (REST) - Meaningless Acronym? Wordplay?
=======================================================================

rest - n. - peace, ease, or refreshment resulting from the insight that the web works

No matter what vendors tell you - no need to "Light Up the Web" - relax - built on
an *open architecture using universal identifiers, formats & protocols and __evolving__
open standards* - no need to reinvent the wheel and sign-up for single-vendor offerings.

### Broad Definition

- Best Practices for Designing Web Services for a Unified Human and Programable Web

### Narrow Definition

- Alternative to BigCo Web Services (SOAP, WS-*) and RPC-Style Web Services (XML-RPC)
~~~

Use `h1` headings to start a new slide - use `h1.` in Textile
or use "underlining" with equal signs (`===`) in Markdown. That's it.
For more formatting options see the Textile or Markdown reference.

### Step 2: Generate your slide show using the `slideshow` gem

Run `slideshow` to generate your slide show. The `slideshow` gem
expects the name of your slide show source document (e.g. `rest`)
without the `.textile` or `.markdown` ending and will generate a web page
(e.g. [`rest.html`](http://slideshow.rubyforge.org/rest.html)
that is an all-in-one-page handout and a live slide show all at once.

~~~
$ slideshow rest

=> Preparing slide show 'rest.html'...
=> Done.
~~~

### Step 3: Open up your slide show in your browser

Open up your slide show [`rest.html`](http://slideshow.rubyforge.org/rest.html)
in your browser (Firefox, Chrome, Safari, Opera and others) and hit F11 to switch 
into full screen projection and hit the space bar or the right arrow, down arrow
or page down key to flip through your slides.

!slideshow.png!:http://slideshow.rubyforge.org/rest.html

That's it. Voila.

### Bonus: Try some different templates/theme packs

* [S6 PDF Theme](http://slideshow.rubyforge.org/tutorial.pdf.html) -> [PDF](http://slideshow.rubyforge.org/tutorial.pdf)
* [Google HTML5 Rocks Theme](http://slideshow.rubyforge.org/tutorial.html5.html)
* [S5 Theme](http://slideshow.rubyforge.org/s5/tutorial.html)
* [Slidy W3C Blue Theme](http://slideshow.rubyforge.org/slidy/tutorial.html)
* [More »](templates.html)

## What's Textile? What's Markdown? What's reStructuredText?   {#textile}

Textile is a wiki-style markup language that's easy-to-write and easy-to-read and
that lets you author web pages in plain text. More:

* [Textile Reference](http://redcloth.org/textile/)

Markdown is another wiki-style markup language that's easy-to-write and easy-to-read and
that lets you author web pages in plain text. More:

* [Markdown Quick Start](http://daringfireball.net/projects/markdown/basics)
* [Markdown Reference](http://daringfireball.net/projects/markdown/syntax)

reStructuredText is yet another wiki-style markup language. More:

* [reStructuredText Quick Reference](http://docutils.sourceforge.net/docs/user/rst/quickref.html)
* [reStructuredText Project Site](http://docutils.sourceforge.net/rst.html)

## What's S5? What's S6?   {#s6}

Simple Standards-based Slide Show System (S5) is
Eric Meyer's (of CSS fame) public domain (free, open source)
slide show package inspired by Opera Show and others that works in all modern browsers
without any plugin required because it includes its own slide show machinery in JavaScript.
(Use the [`s5blank`](http://github.com/geraldb/slideshow-s5-blank)
or [`s5themes`](http://github.com/geraldb/slideshow-s5-themes) theme pack
to create S5 slide shows.)

* [S5 Project Site](http://meyerweb.com/eric/tools/s5)

S6 is the rewrite of Eric Meyer's S5 using
the jQuery JavaScript library - offering easier to understand and easier
to extend code. Add plugins, effects and more. Contributions welcome!

* [S6 Project Site](http://github.com/geraldb/s6)

Keyboard controls:

|_. Action             |_. Key |
| Go to next slide     | Space Bar, Right Arrow Down Arrow, Page Down  |
| Go to previous slide | Left Arrow, Up Arrow, Page Up |
| Go to first slide    | Home |
| Go to last slide     | End |
| Toggle between slideshow and outline view (==&#216;==) | T |
| Show/hide slide controls (==&#216; &laquo; &raquo;==)  | C, Move mouse to bottom right corner |


## What's FullerScreen? What's Opera Show?   {#fullerscreen}

FullerScreen is a free Firefox browser addon that turns your web page in a full screen slide show without
requiring any JavaScript. (Use the [`fullerscreen`](http://github.com/geraldb/slideshow-fullerscreen) theme pack
to create FullerScreen-compatible slide shows.)
More:

* [FullerScreen Firefox Addon Page](https://addons.mozilla.org/en-US/firefox/addon/4650)
* [FullerScreen Documentation](http://disruptive-innovations.com/zoo/fullerscreen/samples/projection-test.html)

Opera Show is the slide show projection machinery built-into the free Opera browser.
Slide Show (S9)-generated web pages using the `fullerscreen` theme pack
are compatible with the Opera Show Format (OSF)
and, thus, your slide shows will work with the Opera browser "out-of-the-box"
without requiring any plugins (just press F11 to get started and page up/down to flip through the slides).

* [Opera Show Documentation](http://www.opera.com/browser/tutorials/operashow/)

## About, License - Questions? Comments?   {#about}

Gerald Bauer and contributors designed and developed the `slideshow` gem.
See the [change log](http://github.com/geraldb/slideshow/blob/master/History.rdoc)
for contributions and credits.

License. The slide show scripts and templates are dedicated to the public domain.
Use it as you please with no restrictions whatsoever.

Questions? Comments? Send them along to the
[Free Web Slide Show Alternatives (S5, S6, S9, Slidy And Friends) Forum/Mailing List](http://groups.google.com/group/webslideshow).
Thanks!