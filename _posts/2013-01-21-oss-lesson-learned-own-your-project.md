---
layout: post
title: "Revive a neglected OSS project"
published: false
---
Doing is learning. In the 3 years or so that I've been involved in [OSS](abbr:Open Source Software), I've only scratched the surface, I'm still just a beginner, but I did learn a lot still. This is a story of open source revival.

## Accept it, you've abandoned this project

It hit me about 6 months ago, as I was receiving the almost-ignored notification email of a Github issue. I'm the maintainer of [Backbone.localStorage](http://github.com/jeromegn/backbone.localstorage), but I haven't done any maintenance in the past year and a half at the least.

### Some causes of OSS orphenage

#### Usage (or lack thereof)

Part of it is because I didn't care. I would care if I was using it. [A very wise man](http://labnotes.org) once taught me that project motivation is directly proportional to your current usage of said project. Since I wasn't using localStorage at all, I wasn't much motivated.

#### Seems like an unsurmountable mountain of work

Issues piled on and pull requests slowly became unmergeable due to higher priority newer ones being merged before. Those are usually the signs of an abandon project. Open source takes time, there's more management to do than you might think.

#### Alien code

As you've merged seemingly good pull requests, you've lost track of how the project is architected. Makes it even more difficult to get back into it, huh? Code styles are disparate, a weird mix of single and double quotes, 2 and 4 spaces indentation (or tabs), and you don't know which one was even yours at the time. It could well have been written by a being out of this world.

## Pass it on to someone who cares

It's alright, you might not want to pursue the grand adventure of [OSS](abbr:Open Source Software). Though before you completely abandon a project, try to find someone who wants to take care of it. This person needs to be chosen carefully. A good place to look is in your pull requests and issues. The best person for the job has probably sent a few pull requests and even replied to a few issues. These people are more interested than you in your project.

I wasn't able to give my project to someone else. I liked open source. I liked giving back too much to do that.

## Revival

So I tacked on my tuque (as people say around [here](http://en.wikipedia.org/wiki/Quebec)) and gave this another try.

### The Great Refactor

First step was to take back control over the code. At least in terms of coding styles and relearning how it all worked.

After a ton of `git blame` and `git diff`, I was starting to get somewhere. In the case of [Backbone.localStorage](http://github.com/jeromegn/backbone.localstorage) (my very first [OSS](abbr:Open Source Software) project), the tests that snuck in were the worst bit. That's cool, at least there were some tests, somebody actually cared enough to contribute tests. I rewrote all of them, that was an easy way to learn how all of that code worked (all 184 lines. I know, not that many.)

Some tests actually testes [Backbone.js](http://backbonejs.org) features. I knew better than to do that. I removed almost half of them and rewrote the other half as clearly and as well as I could from my past experience. I chose [mocha](http://visionmedia.github.com/mocha) because I knew it best.

### Tidying up issues

