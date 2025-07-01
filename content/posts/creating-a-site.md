+++ 
draft = false
date = 2025-07-01
title = "Creating a Personal Website"
description = ""
authors = ["Sable Ayala"]
tags = ["tech", "blog", "website"]
categories = ["technology", "misc"]
series = ["blog"]
math = true
+++

## What's the point of a personal website?

I mean why would I even want to write a personal website? It takes so much effort if I want to do it without a service like Wix or Google Sites. To me the main advantage of writing my own website is that I get to pick and choose how I want it.

For example: with these standard website makers I can't have the cool typing effect that I have on my homepage, and it still took minimal effort.

The code for it looks a little bit like this

```js {linenos=inline}
new TypeIt("#info", {
  waitUntilVisible: true,
})
  .type("Student | Pharmacy Technician")
  .go();
```

And yes it's some work to research this but think about the cool payoff I get. Also I get to write a custom blog like this where I can have whatever theme I want and create highlighting however I want.

Also I'm just a little ADHD and like to have something to do. Being able to work on my own website like this gives me a creative outlet and lets me just put my problem solving to use, because what if the preset set theme that I chose doesn't have exactly what I want?

In that case I get to research the theme and make my own file that has a carbon coby but with the changes that I want, and it will be put in place of the original template. It gives me so much freedom to exercise my brain and let me do whatever I want essentially. It's also a place I get to write when I want to write, even if it's for lame stuff like this.

One of the more interesting options is that if you're like me, you want a website just to be able to put it on your resume and have a downloadable and interactable pdf version on the website. It makes me feel a lot cooler and a lot more professional. All in all it's pretty easy and it allows me to do cool stuff, a lot of people have premade tools that let me do it in a way like this:

```js
{{</* embed-pdf url="../images/resume.pdf" */>}}
```

The single most important reason for me-- I get to have fun with stuff like [Katex](https://katex.org/) which is a rendering engine that allows me to play around with [$\LaTeX$](https://www.latex-project.org/about/) and lets me write both chemical and math equations so if I ever decide to write about something I study in university or write about my job I can still write them like this!

$$
\frac{Volume}{Rate} = \frac{21,000mcg}{10 (mcg)(kg)(min)^{-1}} = Time
$$

I can even write more advanced equations like Maxwell's Equations!

$$
\boxed{
  \begin{align*}
  &  B'=-\nabla \times E,            \\
  &  E'=\nabla \times B - 4\pi j
  \end{align*}
}
$$

Basically, in short, if you're like me and you like giving yourself a hard time for the sake of something slightly more interesting than what you get in 30 seconds, making a website is great for you.

## How to make one?

Well if you're trying to make a statically hosted website like I am, which means it is essentially just some html and javascript with no calls to a server then it's pretty easy. You can either write it all by hand (which I don't recommend) or you can use a static site generator like I do. I am using [Hugo](https://gohugo.io/) which is written and is based in [Go](https://go.dev/) but there's a variety of options that allow you to write your website in all kinds of languages using all kinds of templating syntax. I just happen to be a fan of Hugo because I think it's nice and easy to start with and doesn't have a super hard learning curve even if you don't know Go. Although later I will write about Go because I think my people should have some sort of understanding of the language given how convenient it is to use for all kinds of tasks. (not to mention... it's quite fast)

Your other option is to make a dynamic website using some frameworks (or again... by scratch if you really want) and hosting it on your own server or on a paid hosting service that will let you make whatever callbacks you want, it can lead to more advanced websites with more capabilities but it does require a little bit of a monetary investment if you want to keep it running. (Maybe one day I'll afford a website like that)