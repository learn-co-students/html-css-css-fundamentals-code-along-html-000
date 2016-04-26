# CSS Fundamentals Code Along

## Objectives

1. Review linking an external CSS file.
2. Review writing selectors.
3. Styling text content.

## Introduction

Building upon previous code alongs, in this exercise you will add an external stylesheet and stylize page elements by coding along with the video provided. This will help you to review the concepts you were introduced to in the previous lessons.

## Instructions

1. Fork this repository.
2. Use Terminal to clone your forked copy.
3. Then change directory into the repository folder.
4. Code along with the provided video below and/or its supplementary reading located below the video. Code everything you see there. Feel free to stop, pause, rewind or fast forward through the content to keep pace.

<iframe width="100%" height="720" src="//www.youtube.com/embed/aA8k-hK8qzg?rel=0&amp;controls=1&amp;showinfo=1" frameborder="0" allowfullscreen></iframe></iframe>

### CSS the Decorator to Your Otherwise Bland HTML Pages

Lets start out by making a new feature branch in Terminal by typing `git checkout -b site-style` and press return. 

#### Creating and Linking An External Stylesheet

Next, let's create a folder for our CSS to live in. In Terminal type `mkdir css` and press return. Then let's create a new stylesheet in this folder by typing `touch css/style.css` and press return. Then bring up the index.html page in your code editor.

Inside the `<head>` element at the top of our page let's create a `<link>` element to connect our CSS stylesheet with our HTML index page. 

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Exceptional Realty Group - Luxury Homes - About</title>
    <link rel="stylesheet" href="css/style.css">
  </head>
  ...
```

On line 6 we used the `<link>` element and set its `rel` attribute to `stylesheet` this tells the browser what the relation is of the thing we are linking to. Then the `href` attribute tells the browser the location of the file giving it the relative path `css/style.css` to our file.

#### Adding HTML5 Support Using Normalize and Modernizr

Let's put CSS on pause for a sec, since we coding in the `<head>` section let's take a moment to add some more support for older browsers that will insure they can handle both HTML5 and CSS3 commands we might use for these site pages.

We will start by adding a link to Normalize first. This will give us a base CSS style for all of our pages. This is important as different browsers have different base styles, so one browser may use one font by default another may use a different one. Linking to Normalize will insure we have the same CSS look and feel in all browsers. You can add the following link into the head section just above our CSS link. By linking to normalize first and then our CSS style second it allows us to override the Normlaize base styles with our own style.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Exceptional Realty Group - Luxury Homes - About</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/4.1.1/normalize.min.css">
    <link rel="stylesheet" href="css/style.css">
  </head>
  ...
```

You can see Normalize was linked on line 6 of the code snippet above, just before our linked stylesheet on line 7.

Next we will link Modernizr a JavaScript file that will add support for HTML5 and CSS3 features we will include. New browses do not require Modernizr, but this is helpful for viewers of our site who are surfing the web on old browsers. The more time that goes by these scripts are less and less neccesary as people are forced to update their browsers.

*Note: This lesson video was shot in 2014 and text included in 2016. If your reading this a few years later you probably no longer require these scripts for older browsers. When in doubt [ask the web](http://stackoverflow.com/questions/29420328/is-modernizr-js-still-useful)*

Here is the complete code for inserting a link to Modernizr included our previous changes:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Exceptional Realty Group - Luxury Homes - About</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/4.1.1/normalize.min.css">
    <link rel="stylesheet" href="css/style.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/modernizr/2.8.3/modernizr.min.js"></script>
  </head>
  ...
```

On line 8 we used a `<script>` element which is used to link to any javascripts you wish to use in your page. we set the `src` attribute to point to modernizr. I linked these scripts by searching for them at [CDNJS](https://cdnjs.com).

...

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-code-along-3' title='Overview'>Overview</a> on Learn.co and start learning to code for free.</p>
