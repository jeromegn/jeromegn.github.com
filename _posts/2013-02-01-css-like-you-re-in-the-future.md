---
layout: default
published: false
title: "Write CSS like you're in the future with Stylus"
---

[Stylus](http://learnboost.github.com/stylus) has many great features. Its best feature it allowing you to write CSS as if you were in the future.

So what does the future hold? Mainly one thing.

## No browser-specific prefixes

Have you ever written something like that?

```css
.something {
  -moz-border-radius: 1em;
  -webkit-border-radius: 1em;
  border-radius: 1em;
  -moz-transition: all 1s ease;
  -o-transition: all 1s ease;
  -webkit-transition: all 1s ease;
  transition: all 1s ease;
  -moz-box-shadow: #123456 0 0 10px;
  -webkit-box-shadow: #123456 0 0 10px;
  box-shadow: #123456 0 0 10px;
}
```

You did if you wanted to support most browsers which support these features. The spec doesn't mention browser prefixing. [They're a solution to a non-issue](http://www.quirksmode.org/blog/archives/2010/03/css_vendor_pref.html). Yet, they are necessary for a few features of CSS3.

Here's how [nib](https://github.com/visionmedia/nib) fixes that with Stylus' seamless mixins:

```css
border-radius(radius){
  -moz-border-radius: radius;
  -webkit-border-radius: radius;
  border-radius: radius;
}

transition(transition){
  -moz-transition: transition;
  -o-transition: transition;
  -webkit-transition: transition;
  transition: transition;
}

box-shadow(){
  -moz-box-shadow: arguments;
  -webkit-box-shadow: arguments;
  box-shadow: arguments;
}
```

Now in your `.styl` file:

```css
@import "mixins";

.something {
  border-radius: 1em;
  transition: all 1s ease;
  box-shadow: #123456 0 0 10px;
}
```

... will output the same CSS as above, all the while following CSS3 specifications.

I love Stylus, this is the first post of many on the subject.