---
layout: default
title: Settings, Tips, Tricks and More
---

# {{ page.title }}

<div class="toc" markdown="1">
Contents:

* [How To Create Slides Without Titles?](#notitle)
* [How To Use Gradient Themes?](#themes)
* [How To Use Your Own Slide Show Template Packages?](#templates)
* [How To Fetch New Template Packages?](#fetch)
* [How To Fetch New Template Packs Using `git`?](#git)
* [How To List All Installed Template Packages?](#list)
* [How To Generate PDF Documents from Your Slide Shows?](#pdf)
* [How To Set Default Command Line Options?](#slideshowopt)
* [How To Comment Out Content?](#comments)
* [Questions? Comments?](#questions)
</div>

## How To Create Slides Without Titles?   {#notitle}

You can use the `!SLIDE` directive to create slides without headings.
Example:

~~~
!SLIDE

A slide with no title

!SLIDE

Another slide with no heading

!SLIDE

And another

!SLIDE commandline

    $ ruby print.rb

!SLIDE image 

!i/friendsbadge.png!
~~~

Note, you can pass along CSS style classes to your generated `div`
or `section` that wraps your slide. Example:

~~~
!SLIDE smaller commandline
~~~

Will become:

~~~
<div class='slide smaller commandline'>
  ...
</div>
~~~


## How To Use Gradient Themes for the Built-In S6 Template Pack?   {#themes}

You can define your gradient theme in plain text in the slide show source in the header
using a simple CSS-style name value pair. [More »](themes.html#use)


## How To Use Your Own Slide Show Template Packages?   {#templates}

Use the `-g/--generate` switch to generate a sample template
package with manifest using the built-in S6 machinery.

Example: Generate a template pack w/ manifest in your working folder 

~~~
$ slideshow -g
~~~

Or fetch a sample template pack from the internet or fork it using `git` or create
it from scratch.
See the [Template Gallery](templates.html) for more info and examples to get started.

To use your own template pack use the `-t/--template MANIFEST` option 
passing along the manifest. Example:

~~~
$ slideshow -t s6.txt  microformats
$ slideshow -t s5blank.txt   microformats
~~~

Got templates? Send a link and announcement to the
[Forum/Mailing List](http://groups.google.com/group/webslideshow)
and get your link added to the [Template Gallery](templates.html).


## How To Fetch New Template Packages?  {#fetch} 

Using the `-f/--fetch URI` option lets you fetch (install) new templates. Example:

~~~
$ slideshow -f http://github.com/geraldb/slideshow-s5-blank/raw/master/s5blank.txt 
~~~

Resulting in:

~~~
Fetching template package 's5blank' 
  : from 'http://github.com/geraldb/slideshow-s5-blank/raw/master 
  : saving to '/home/gerald/.slideshow/templates/s5blank' 
  Downloading manifest 's5blank.txt'... 
  Downloading template 'header.html.erb'... 
  ... 
  Downloading template 'ui/default/slides.js'... 
Done. 
~~~

Note, if you want to store the template pack somewhere else
use the `-c/--config` option (defaults to `~/.slideshow`).

To find more templates browse the [Template Gallery](templates.html).


### Troubleshooting

Trouble downloading? Do you have a direct internet connection?
If not, configure your proxy using the HTTP_PROXY environment variable. Sample:

~~~
HTTP_PROXY=http://234.445.454:4341
~~~

Or with user credentials (that is, login and password):

~~~
HTTP_PROXY=http://gerald:topsecret@234.445.454:4341
~~~

If all fails, you can always download the template pack on your own
(using lets say `git` itself) and than move the souces into your
templates folder (that is, `~/.slideshow/templates`).


## How To Fetch New Template Packs Using `git`?   {#git}

If you prefer you can fetch template packs using `git` itself in two steps

Step 1: Change to your templates folder

Issue the command:

~~~
cd ~/.slideshow/templates
~~~

Step 2: Clone (Fetch) the template pack using `git`

Let's clone the `slideshow-google-html5-slides` template pack.
Issue the command:

~~~
git clone http://github.com/geraldb/slideshow-google-html5-slides.git
~~~

That's it. Use the `-l/--list` option to list all you installed template packs.

## How To List All Installed Template Packages?   {#list}

Using the `-l/--list` option lets you list all installed templates. Example:

~~~
$ slideshow -l
~~~

Resulting in:

~~~
Installed templates include: 
  s5blank.txt       (/home/gerald/.slideshow/templates/s5blank/s5blank.txt) 
  s5.txt            (/usr/lib/ruby/gems/1.8/gems/slideshow-0.8/templates/s5.txt) 
  s6.txt            (/usr/lib/ruby/gems/1.8/gems/slideshow-0.8/templates/s6.txt) 
  fullerscreen.txt  (/usr/lib/ruby/gems/1.8/gems/slideshow-0.8/templates/fullerscreen.txt) 
~~~


## How To Generate PDF Documents from Your Slide Shows?   {#pdf}

When you generate your slide show as usual with the built-in S6 template pack
you will get an extra `<your_name_here>.pdf.html` document generated that
you can use to generate a PDF-version of your slide show
using lets say the free, open source [`wkhtmltopdf`](http://code.google.com/p/wkhtmltopdf/) tool.

Example:

~~~
$ slideshow tutorial

$ wkhtmltopdf --outline --orientation Landscape tutorial.pdf.html tutorial.pdf 
~~~


## How To Set Default Command Line Options?   {#slideshowopt}

The `SLIDESHOWOPT` environment variable lets 
you set default command line options.

Example: Make `slides` your default output folder

~~~
$ SLIDESHOWOPT=-o slides
~~~

Example: Make S5-compatible slide show

~~~
$ SLIDESHOWOPT=-o slides -t s5blank.txt
~~~

Example: Make your own template package the default

~~~
$ SLIDESHOWOPT=-t <your_template_manifest_here>
~~~

And than use the gem executable as usual (will use/add your command line 
options stored in `SLIDESHOWOPT`):

~~~
$ slideshow microformats
~~~


## How To Comment Out Content?   {#comments}

Use `%` for comments anywhere (including headers) and `%begin`/`%end`
for multi-line comments and `%end` to skip everything until the end.

~~~
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%  Start off with some headers

title: 10 Things Every Java Programmer Should Know About Ruby
author: Jim Weirich

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%  Let's go. The presentation starts here

# 10 Things Every Java Programmer Should Know About Ruby

Jim Weirich
~~~

See [10 Things Every Java Programmer Should Know About Ruby](http://github.com/geraldb/slideshow/blob/master/samples/3rd/10things.text)
sample.

Note, as an alternative syntax to skip (comment out)
content in your source enclose it with  `__SKIP__`/`__END__`. Example:

~~~
__SKIP__ 
  not yet ready or private notes/comments 
__END__ 
~~~

As a shortcut if you just use `__END__` (without `__SKIP__`) (Ruby-like)
it will skip everything from `__END__` until the end of the file.

## Questions? Comments?   {#questions}

Questions? Comments? Send them along to the
[Free Web Slide Show Alternatives (S5, S6, S9, Slidy And Friends) Forum/Mailing List](http://groups.google.com/group/webslideshow).
Thanks!