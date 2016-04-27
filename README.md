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

On line 8 we used a `<script>` element which is used to link to any javascript files. There we set the `src` attribute to point to Modernizr. I linked these scripts by searching for them at [CDNJS](https://cdnjs.com).

#### Comments

Next, open up your style.css file in your code editor. Let's start by writing a comment.

```css
/* This
is 
a comment */
```

So remember from our previous lesson we can see that CSS comments start with a `/*` and end with a `*/`. These comments can be single or or across multiple lines like the example above. 

#### Syntax

Next let's create a comment to review CSS syntax,

```css
/* CSS Syntax:

selector {
  property: value;
  porperty: value;
}

*/
```

CSS is made up of a **selector** statement that selects elements within our HTML page. This is followed by a set of `{}` curly braces. Every declaration (CSS rule) within the braces will be applied to the element specified in the **selector**. Inside the braces we have declarations (CSS rules) that are made up of a **property** then a `:` colon, followed by a **value** and ended with a `;` semicolon.

#### Type Selector

Suppose you wanted to select all paragraphs in your HTML page. We can do so using a type selector thaht will select all elements with the matching type (element name).

```css
p { 
  font-size: 16px;
}
```

By simply giving the element name `p` as the selector it will select all `<p>` elements within our linked HTML page(s). On line 2 we used the `font-size` property which will adjust the font-size in our case on all our paragraphs. This property accepts values measured in `px` pixels, `pt` points, `%` percents, and `em` ems.

Pixels will size type consistently across different browsers. Point size varies from browser to browser and is not reccomended for szing type. Percents are an adjustable amount and depends on the sizing of other parent elements. Ems are also an adjustable amount that is dependent upon parent elements sizing. Ems in most browsers have the following realtionship to pixels where 1 em = 16px. In responsive website design which we will discuss in a later lesson, we will see that there are some key advantages to sizing your typography using ems. To convert pixels to ems you just need to divide by 16. So 16px / 16 = 1em. Let's update this in our code

```css
p { 
  font-size: 1em;
}
```

Next let's add a line height. This is the sapcing between lines of text in the paragraph.

```css
p { 
  font-size: 1em;
  line-height: 1.5em; 
}
```

If you save the page and head back to the browser and bring up the index page you will notice our paragraph text has been adjusted. Let's also adjust the CSS for `<figcaption>`.

```css
figcaption {
  font-weight: normal;
  font-size: 0.75em;
  line-height: 1.5em;
  font-family: Georgia, "New Times Roman", serif;
}
```

A few new font properties we have introduced here are `font-weight` on line 2. This as you probably guessed adjusts the thickness of the text. It can be set to numbers in increments of one hundred from 100 to 900, 900 being the thickest. you can also specify lighter, light, normal, bold, or bolder. You can also sepcify initial (which sets it to its default value), or inherit (which sets it to inherit the thickness of its parent element). On line 5 of the snippet above we used `font-family` property to change the font applied to our text. We can give this a `,` comma separated list of values for each font to look for. If the user does not have the first font to the left it will try the next to the right and so on and so forth until it finds a matching font that exists on their system.

In CSS we can replace all of the previous font properties set on `figcaption` by usinhg the `font` short-hand property instead.

```css
figcaption {
  /*font-weight: normal;
  font-size: 0.75em;
  line-height: 1.5em;
  font-family: Georgia, "New Times Roman", serif;*/
  font: normal 0.75em/1.5em Georgia, "New Times Roman", serif;
}
```

Next, let's set a color and text alignment on our `figcaption`

```css
figcaption {
  /*font-weight: normal;
  font-size: 0.75em;
  line-height: 1.5em;
  font-family: Georgia, "New Times Roman", serif;*/
  font: normal 0.75em/1.5em Georgia, "New Times Roman", serif;
  color: #777;
  text-align: right;
}
```

On line 6 of the code snippet above we set the color of our text using the `color` property. This property accepts color names, hexidecimal, rgb, rgba, hsl, and hsla color values. In our case we will set it to a hexidecimal value `#777` which is a shade of gray. Please refer to the previous lesson on color values for more details on all the possibilities of how to assign color in CSS. On line 8 of the code snippet above we ste the text to align to the right side of the element (flush right).

#### Web Fonts

So far we have used the `font-family` property to set the font on our text asuuming the user has the font file for that particular font on their computer. One way to insure that we can use a specialized font that users may not have on their system is to load a web font. Using this strategy involves providing the font as part of the files in your website and telling the browser to load the font for use in the webpages. An easy way to include web fonts is to link to them from other websites. In this example we will use Google Fonts which provides links to access their free font library. 

Start by heading over to [http://google.com/fonts](http://google.com/fonts) in your browser. Then, in the search bar on this page search for `Elsie`. From the returned search results under "Elsie Swash Caps" next to the Add to Collection button there are three icons. Click the center icon "quick-use". 

Under the box that says "1. Choose the styles you want", check the boxes for both Normal 400, and Ultra Bold 900.

Then scroll to the bottom and under "3. Add this code to your website:" click the "@import" tab and copy the code to your clipboard. Command + c (Mac) or Ctrl + c (Windows). Then head back to the style.css file in your code editor and paste the code Command + v (Mac or Ctrl + v (Windows) at the very top of your file on line 1. it should look like the following:

```css
@import url(https://fonts.googleapis.com/css?family=Elsie+Swash+Caps:400,900);
```

It is important to place imported fonts code at the top of the file so you can refer to it further down in the css file.
Let's repeat those same steps we did to get the Elsie Swash Caps font, but we'll do the same for Clicker Script.

```css
@import url(https://fonts.googleapis.com/css?family=Elsie+Swash+Caps:400,900);
@import url(https://fonts.googleapis.com/css?family=Clicker+Script);
```

Now at the top of our style.css document we are linking to two different Google web fonts.

Back on the Google font page you'll see how to apply the font to an element by setting it as a font on the `font-family` property. In the case of Elsie Swash Caps we would need to include `font-family: 'Elsie Swash Caps', cursive;` on any element we want to style with this font and `font-family: 'Clicker Script', cursive;` for any elements we wish to apply Clicker Script to. To demonstrate, let's add Elsie to our `figcaption` replacng the previous font of Georgia, serif.

```css
figcaption {
  /*font-weight: normal;
  font-size: 0.75em;
  line-height: 1.5em;
  font-family: Georgia, "New Times Roman", serif;*/
  font: normal 0.75em/1.5em 'Elsie Swash Caps', cursive;
  color: #777;
  text-align: right;
}
```

#### Class Selector

...

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/fe-code-along-3' title='Overview'>Overview</a> on Learn.co and start learning to code for free.</p>
