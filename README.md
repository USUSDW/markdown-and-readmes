# Markdown and Readmes
*By Hunter Henrichsen*

## Table of Contents
  * [Introduction](#introduction)
  * [Basic Formatting](#basic-formatting)
    + [Inserting Code](#inserting-code)
    + [Inline Formatting](#inline-formatting)
  * [Rendered Markdown](#rendered-markdown)
    + [Links](#links)
    + [Lists](#lists)
    + [Tables](#tables)
    + [Images](#images)
    + [HTML Embedding](#html-embedding)
  * [Building Attractive Readmes](#building-attractive-readmes)
    + [Utilities](#utilities)
  * [GitHub Profile Readme](#github-profile-readme)

## Introduction

Markdown is a language that's used in many places nowadays. It's a pretty
simple set of tools that depending on circumstance can be very powerful.
It's used in applications like Slack, Discord, and on websites like GitHub.
Building a parser for Markdown isn't super complicated, as most of the time it
just gets rendered down into HTML anyways. Let's start at the basics and work
our way up to more advanced things.

Paragraphs are denoted by skipping two lines. This means that text that's only
one line apart is kept together which is nice for some editors or terminals
where you can only display so many characters without lines becoming confusing.
I like to keep mine around 80 characters wide, and then break after that. I
have Vim configured to automatically wrap onto new lines, and other editors can
be configured to do the same. It's super nice.

## Basic Formatting
So paragraphs can be broken up pretty easily. Let's talk about basic formatting.
Markdown gives us five levels of headers to break our documents up into
different sections. The number of hashes before the title tells us how high in
the hierarchy it is. One hash means that it's the first level in the hierarchy.
Two falls below one, and so on.

### Inserting Code

Underneath headings, we sometimes need to do different things. The first thing
that I frequently find myself doing is inserting code into a document. We like
code to both stand out, and ignore any other formatting. In markdown, we do 
that with backticks, like this:

```md
`print("Hello!")`
```

This will produce this: `print("Hello!")`

If we want a block of code with multiple lines, we instead use triple backticks:

    ```
    This is a block of code.
    ```

Another option is to just indent the code by 4 spaces. That's how I got the 
above code working.

An added benefit of the backtick method, however, is that we can instruct 
whatever is interpreting our markdown to highlight the code with a specific 
language. We do that by putting the language name on the first set of triple
backticks, like so:

    ```python
    import math
    
    def printPi():
        print(math.pi)

    printPi()
    ```

Which gives us the following:
```python
import math

def printPi():
    print(math.pi)
    
printPi()
```

### Inline Formatting

Another pretty universal feature to markdown is inline formatting. Some more 
"advanced" types of formatting are unique to sites where it's actually rendered
on a webpage. Unfortunately, formatting will sometimes depend on what is used to
parse the markdown. I wish things were more standard (and that more platforms 
than Discord supported underscore), but I'd just end up creating 
[another standard](https://xkcd.com/927/).

| Platform               | Symbol | Amount | Result        | Example       |
|------------------------|--------|--------|---------------|---------------|
| Discord, GitHub        | `*`    | 1      | Italic        | `*Example*`   |
| Slack                  | `*`    | 1      | Bold          | `*Example*`   |
| Discord, GitHub        | `*`    | 2      | Bold          | `**Example**` |
| Discord, GitHub, Slack | `_`    | 1      | Italic        | `_Example_`   |
| Discord                | `_`    | 2      | Underline     | `__Example__` |
| GitHub                 | `_`    | 2      | Bold          | `__Example__` |
| GitHub, Discord        | `~`    | 2      | Strikethrough | `~~Example~~` |


## Rendered Markdown

Now we move on into some more advanced features. These are supported on sites
like GitHub and Dev.to, but not as much on messaging services like Discord and
Slack. 

### Links

Links are super cool. I wish I could label links when I sent them to people in
Discord or other services. Alas, they've thwarted my attempts to rickroll people
with innocent looking link titles. GitHub isn't as strict, so it allows me to
embed links like this:

```markdown
[Google Homepage](https://google.com)
```

### Lists

Lists are another thing I wish was more supported in messaging apps. I've 
resorted to copying the unicode bullet character (`•`) and pasting it where I 
need it, but some places (like GitHub) will do this for us. We just start a line
with a star and a space after it and we get a nicely-rendered list.

```markdown
Grocery List:
* Eggs
* Milk
* Wheaties
```

Grocery List:
* Eggs
* Milk
* Wheaties

Numbered lists work a similar way. If a line starts with a number and then a 
period, it'll get tied into whatever list is around it:

```markdown
1. First Item
1. Second Item
6. Third Item
```

1. First Item
1. Second Item
6. Third Item

### Tables

Tables are supported in Markdown as well, and are pretty useful when you can
remember the formatting for them. I struggle to do that, but here's one anyways:

```markdown
| Platform        | Symbol | Amount | Result | Example       |
|-----------------|--------|--------|--------|---------------|
| Discord, GitHub | `*`    | 1      | Italic | `*Example*`   |
| Slack           | `*`    | 1      | Bold   | `*Example*`   |
| Discord, GitHub | `*`    | 2      | Bold   | `**Example**` |
```

### Images

Images work just like links in markdown, just with an exclamation before the
link to the image.

```markdown
![Mystery image.](https://i.imgur.com/yeBmKcY.gif)
```

### HTML Embedding

Fed up with not being able to do something in Markdown? Markdown has you 
covered! Since it renders down to HTML, you can include HTML in the Markdown
and it'll be rendered in the finished product. This is an important piece in
creating attractive readmes and GitHub profile readmes.


## Building Attractive Readmes

Before I try and do anything, I try and look for examples of what I'm trying to
do. No need to reinvent the wheel, and if I know a readme looks good, I can 
usually borrow some element from it.

Good Examples:
<!-- Man, my bias is really showing here... -->
* [Koa](https://github.com/koajs/koa#readme)
* [Express](https://github.com/expressjs/express#readme)
* [Nord](https://github.com/arcticicestudio/nord#readme)
* [Choo](https://github.com/choojs/choo#readme)
* [Zircon](https://github.com/Hexworks/zircon#readme)
* [Release It](https://github.com/release-it/release-it#readme)
* [And Many More...](https://github.com/matiassingers/awesome-readme/blob/master/readme.md)

Another nice thing about GitHub is that you can go into these repositories and
view the source code of their readme by clicking the "Raw" button up near the
top.

So what are some of the things they're doing well?

Here's what I think:

* Some sort of title/logo at or near the top.
* Some kind of demo, whether that's code or an animated gif.
* Instructions for getting set up or including it in a project.
* Badges showing off build status, test coverage, and other stats.
* Ease of navigation. 

### Utilities
* [Shields.io](https://shields.io) - Badges in a variety of formats.
* [Asciinema](https://asciinema.org/) - Record your terminal from your terminal.
* [svg-term-cli](https://github.com/marionebl/svg-term-cli) - Use an animated 
svg instead of a gif.

## GitHub Profile Readme
Even if you don't have some fancy project that you're trying to get other 
developers to use on GitHub, you can still put these skills to good use. GitHub
has a secret little feature where if you create a repo that has the same name as
your username, it'll draw the contents of your readme to your GitHub profile 
page. Mine can be found [here](https://github.com/hhenrichsen).