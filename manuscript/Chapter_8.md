#Chapter 8 Project: Create the Tesla Homepage

##Tesla Homepage Clone Overview and Instructions

This guide walks through the project requirements for the Tesla homepage clone project, including the overview of what we are going to build along with how to get resources such as the SVG image.

In this section, we're going to go over Project 4, which is recreating the Tesla homepage.  At the time of creating this tutorial, the Tesla homepage looked like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Tesla+Homepage+Clone+Overview+and+Instructions/image1.png)

But, now it has changed, though some elements are still common.

You can decide which web page you want to clone - the above one or the current one. It doesn't really matter because you'll still learn quite some concepts, and the experience of building such a live site can come handy for your future projects.

The key items are:

Header that includes a logo, a left navigation bar and a center navigation bar, though both the bars look slightly different from each other.

The image in the center - "P100D". This is not a traditional image, rather it is a SVG or a vector made up of many different points. If you right click on the page and see the source, you'll see a number of points that make up this image.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Tesla+Homepage+Clone+Overview+and+Instructions/image2.png)

If you're trying this out on your own, I'd recommend you find a SVG image and integrate it with the file. It'll be a good learning experience.

If you can't find any image, go to the show notes, and there you'll see a link to "https://github.com/jordanhudgens/tesla-html-css-clone". Here you'll see the `index.html` file, and feel free to take the SVG image from it. However, don't look at the rest of the code because I think the best way to learn something is by making mistakes and coming up with your own solutions to fix them.

The next item is a large high resolution image as the background.

A footer that contains a few links and the image of a flag.

So, good luck building this webpage. Once you're done, we'll go through my solution together.

### Resources
- [Images for website](https://github.com/jordanhudgens/tesla-html-css-clone/tree/master/img)

##Project Solution: Tesla Homepage HTML Structure

In this solution we'll walk through how to build the HTML tag structure and integrate the content for the Tesla homepage project.

I hope you've tried building the site by yourself. In this guide, we'll go through my solution.

 As always, let's start with a basic HTML structure that includes `<!DOCTYPE>`, `<html>`, `<head>`, `<title>`, and `<body>` tags.

Inside the `<body>` tag, we'll start with a container `<div>`. Inside this tag, let's start building our header.  If you remember, we have a logo and two sets of nav bars. We need only one `<ul>`, and inside this, we can place all that we need.  This tag will have a `<div>` for logo, and an `<img>` tag for the image. You can grab the images from img directory in "https://github.com/jordanhudgens/tesla-html-css-clone". You can also use your own images.  

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Tesla Clone</title>
  </head>

  <body>
    <div id="container">
      <div id="header">
        <ul>
          <div id="logo">
            <img src='img/logo.png' alt="logo" />
          </div>
        </ul>
      </div>
    </div>
  </body>

</html>
```

Next, we'll create our first set of nav buttons, which is the left navigation bar.  We'll create a class for these navigation elements, as all of it have similar styles.

```html
<ul>
  <div id="logo">
    <img src='img/logo.png' alt="logo" />
  </div>

  <div>
    <a href="#" class="nav-button">Model S</a>
    <a href="#" class="nav-button">Model X</a>
    <a href="#" class="nav-button">Model 3</a>
    <a href="#" class="nav-button">Charging</a>
    <a href="#" class="nav-button">Energy</a>
  </div>
</ul>
```

Let's see how it looks on the browser.

If you're wondering about the logo, don't worry! This logo is white, and this is why you can't see it on the browser. If you're still not convinced, right-click on the page and click on inspect. You should be able to see the code now.

We'll duplicate this code for our right navigation buttons, and change the content.

```html
<ul>
  <div id="logo">
    <img src='img/logo.png' alt="logo" />
  </div>

  <div>
    <a href="#" class="nav-button">Model S</a>
    <a href="#" class="nav-button">Model X</a>
    <a href="#" class="nav-button">Model 3</a>
    <a href="#" class="nav-button">Charging</a>
    <a href="#" class="nav-button">Energy</a>
  </div>

  <div id="right-nav-buttons">
    <a href="#" class="nav-button">Updates</a>
    <a href="#" class="nav-button">Support</a>
    <a href="#" class="nav-button">Find Us</a>
    <a href="#" class="nav-button">Shop</a>
    <a href="#" class="nav-button">My Tesla</a>
  </div>
</ul>
```

You can also use `<li>` tags instead of `<div>`. Its completely up to you.  With that, our header is done.

The next section is the center content, including the SVG. We'll create a `<div>` tag, and inside this, another `<div>` tag for our SVG image. I'm going to cop paste it from a different file, but just remember that it's nothing but a series of CSS style points and vectors.

```html
<div id="content">
  <div id="banner">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 257.1 41.8">
      <style>.st0{fill:#BCBEC0;} .st1{fill:#ED1C24;} .st2{fill:#D1D3D4;}</style>
      <path d="M256.3 40.7c0 .6-.5 1.1-1.1 1.1H2.2c-.6 0-1.1-.5-1.1-1.1v-1.2c0-.6.5-1.1 1.1-1.1h253c.6 0 1.1.5 1.1 1.1v1.2zM139.2 13.9l-.1-1.3-.3-1.3-.4-1.2-.4-.8-.5-.8-.6-.7-.6-.6-1-.7-1-.6-1.1-.5-1.8-.6-1.9-.4-1.9-.4-1.8-.1H124l-5.4-.1h-7.3l-2 .2-1.9.2-1.9.4-1.9.6-1.2.5-1.1.6-1.1.8-1 .9-.9 1-.7 1.1-.6 1.2-.4 1.2-.3 1.3-.3 1.9-.1 1.9v.8l-.1 1.8.1 1.8.2 1.2.3 1.2.4 1.2.5.8.6.8.6.7.7.6 1 .7 1.1.6 1.1.5 1.8.5 1.9.4 1.9.2 1.9.1 1.9.1 5.4.1h5.4l1.9-.1 1.9-.1 1.9-.2 1.7-.3 1.8-.6 1.1-.5 1.1-.6 1-.7.7-.6.6-.7.6-.7.5-.8.6-1.2.4-1.3.3-1.3.2-1.9.1-1.9.1-.8.1-1.8v-1.7zm-8.9 3l-.1 2.1-.2 2.1v.1l-.3 1.4-.4 1.4-.3.7-.4.7-.5.6-.5.5-.1.1-.7.5-.8.5-.8.4-.9.3-1.2.2-1.2.1h-5.1l-3.9-.1h-1.2l-1.1-.1-1.1-.2-.8-.2-.8-.3-.7-.4-.6-.5-.1-.1-.5-.5-.5-.6-.4-.7-.3-.7-.3-1-.2-1-.1-1V19l.1-2.1.2-2v-.2l.3-1.5.5-1.5.7-.7.4-.7.5-.6.5-.5.1-.1.7-.5.8-.4.8-.4.9-.3 1.2-.2 1.2-.1 1.2-.1h4l3.9.1h1.2l1.1.1 1.1.2.8.2.8.4.7.5.6.6.1.1.4.6.4.6.3.7.2.7.3 1.5.1 1.5v2zm58.5-3l-.1-1.3-.3-1.3-.4-1.2-.4-.8-.6-.9-.6-.7-.6-.6-1-.7-1-.6-1.1-.5-1.8-.6-1.9-.4-1.8-.3-1.8-.1-1.8-.1-5.4-.1h-7.3l-2 .3-1.9.2-2 .4-1.9.6-1.1.6-1.1.6-1.1.8-1 .9-.9 1-.7 1.1-.6 1.2-.4 1.2-.3 1.3-.3 1.9-.1 1.9v.8l-.1 1.8.1 1.8.2 1.2.3 1.2.4 1.2.5.8.6.8.6.7.7.6 1 .7 1.1.6 1.1.5 1.8.5 1.9.4 1.9.2 1.9.1 1.9.1 5.4.1h5.4l1.9-.1 1.9-.1 1.9-.2 1.9-.4 1.8-.6 1.1-.5 1.1-.6 1-.7.7-.6.6-.7.6-.7.5-.8.6-1.2.4-1.3.3-1.3.2-1.9.1-1.9.1-.8.1-1.8-.2-1.7zm-8.9 3l-.1 2.1-.2 2.1v.1l-.3 1.4-.4 1.4-.3.7-.4.7-.5.6-.5.5-.1.1-.6.5-.8.5-.7.4-.9.3-1.2.2-1.2.1h-5.1l-3.9-.1h-1.2l-1.1-.1-1.1-.2-.8-.2-.8-.3-.7-.4-.6-.5-.1-.1-.5-.5-.5-.6-.4-.7-.3-.7-.3-1-.2-1-.1-1V19l.1-2.1.2-2v-.2l.3-1.5.5-1.5.3-.7.4-.7.5-.6.5-.5.1-.1.7-.5.8-.4.8-.4.9-.3 1.2-.2 1.2-.1 1.2-.1h4l3.9.1h1.2l1.1.1 1.1.2.8.2.8.4.7.5.6.6.1.1.4.6.4.6.3.7.2.7.3 1.5.1 1.5v2zM89.3 28.8c-1.6-.3-2.8-.6-3.1-1.6-.1-.3-.1-.6-.2-1v-3.7c0-.7.3-6.9.3-6.9l.6-11.4H71.5l-.1 2.7c1 .1 2 .2 3 .4 1.6.3 2.8.6 3.1 1.6.1.3.1.6.2 1v4.4c0 .5-.2 3.9-.3 6.2-.1 1-.5 5.3-.6 5.7-.1.4-.2.7-.3 1-.4 1.1-1.7 1.4-3.3 1.6-1 .2-2 .3-3.1.4l-.1 2.7h22.2l.1-2.7c-1-.1-2-.2-3-.4z" class="st0"/>
      <path d="M2 31.3c-.5 0-1-.4-1-1v-.7c0-.5.4-1 1-1 0 0 3.9 0 6.2-1.6 0 0 .4-.3.5-.9.1-.7.5-4.5.5-10.4 0 0 0-.4.2-.7.2-.2.4-.3.7-.3h25.7c2.2 0 13.3-.3 13.3-5.5 0-5.7-15-5.8-15.7-5.8H4.8c-.2 0-.4 0-.7-.2-.3 0-.9-.4-2.7-.6-.4 0-.8-.3-.8-.9v-.2s0-.3.2-.6c.1-.1.3-.3.7-.3H34c2 0 8.9.1 15.2 1.2 8.4 1.5 12.7 4.1 12.7 7.8 0 8.2-21.2 9.2-37.1 9.2h-1.6c-.2 0-1 .1-1 1.3 0 1.9.2 5.4.2 5.4 0 .4.1.9.1 1.1.5.7 2.2 1.2 3.5 1.4 3.3.6 6.3.6 6.4.6.5 0 1 .3 1 1v.6c0 .1 0 .5-.3.8-.1.1-.4.3-.7.3H2z" class="st1"/>
     <path d="M34 1.2c4 0 27.3.3 27.3 8.4 0 8.4-25.6 8.6-36.5 8.6h-1.6s-1.6 0-1.6 1.9.2 5.5.2 5.5 0 1.1.2 1.3c.2.2.6 1.1 3.9 1.7s6.5.6 6.5.6c.1 0 .4 0 .4.4v.6s0 .5-.4.5H1.9s-.4 0-.4-.4v-.7s0-.4.4-.4 4.2-.1 6.6-1.7c0 0 .6-.4.7-1.3s.5-4.7.5-10.4c0 0-.1-.5.4-.5h25.7c2.8 0 13.9-.4 13.9-6.1C49.8 3.1 35.1 3 33.6 3H4.7c-.1 0-.2 0-.4-.1-.2-.2-.8-.6-2.8-.9 0 0-.3 0-.3-.3v-.2s0-.3.3-.3l32-.1c-.1.1.1.1.5.1M34 0h-.6L1.4.1C1 .1.6.2.4.5c-.3.3-.4.7-.4 1v.2C0 2.4.6 3 1.4 3.1c1.6.3 2.1.6 2.4.7h.1c.4.2.7.3 1 .3h28.8c6.1 0 15.1 1.4 15.1 5.2 0 4.8-11.4 4.9-12.8 4.9H10.3c-.5 0-.9.2-1.2.5-.4.4-.4.9-.4 1.2 0 5.7-.4 9.5-.5 10.2 0 .3-.2.4-.2.4C6.1 27.8 3 28 2 28s-1.6.8-1.6 1.5v.7c0 1 .8 1.5 1.5 1.6h30.5c.5 0 .9-.2 1.2-.5.4-.5.4-1 .4-1.2v-.5c0-.9-.7-1.6-1.6-1.6-.4 0-3.2-.1-6.2-.6-1.9-.4-2.8-.8-3.1-1.1 0-.2-.1-.6-.1-.8 0 0-.2-3.6-.2-5.4 0-.2 0-.5.1-.6.1-.1.3-.1.3-.1h1.6c17.5 0 37.7-1.1 37.7-9.7C62.5.7 40.7 0 34 0z" class="st2"/>
      <path d="M226.3 32.1h-29v-3.8h.6c1.8 0 3.1-.5 4-1.4 1.1-1.2 1.1-2.8 1.1-2.8V13.3h11.5v11.2c0 2.9 2.1 3.3 2.2 3.3 2 .2 4.2.3 6.4.3 6.3 0 21.1-1 21.1-10.7 0-9.1-19.6-9.8-25.7-9.8H199v-4h22.3c8.6 0 15.9.7 21.6 2.1 9.1 2.2 13.8 6.2 13.8 11.7-.1 14-25.3 14.7-30.4 14.7z" class="st1"/>
      <path d="M221.2 4.2c10.8 0 34.7 1.1 34.7 13.2 0 13.5-25 14.1-29.7 14.1h-28.5v-2.7c5.9 0 5.6-4.8 5.6-4.8V13.9h10.3v10.6c0 3.5 2.7 3.9 2.7 3.9 1.9.2 4.1.3 6.5.3 9.6 0 21.7-2.1 21.7-11.3 0-9.6-19.8-10.4-26.2-10.4h-18.9V4.2h21.8m0-1.2h-22.9v5.3h20.1c4.2 0 25.1.4 25.1 9.2 0 9.2-14.3 10.2-20.5 10.2-2.7 0-4.9-.2-6.3-.3-.3-.1-1.7-.5-1.7-2.8V12.7h-12.7v11.4s0 1.4-.9 2.4c-.7.8-1.9 1.2-3.5 1.2h-1.2v5.1h29.7c5.1 0 30.8-.7 30.8-15.3-.1-6.7-6.3-14.5-36-14.5z" class="st2"/>
  </svg>
</div>
```

If you look through this code, you'll see some CSS classes and vector points, and this is what make up an SVG image.

If you refresh the page, you'll see the image.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Tesla+Homepage+HTML+Structure/image2.png)

The next will be a `<div>` tag for our marketing content. We'll probably have separate `<div>` tags for each line of content.

```html
<div id="marketing-content">
  <div id="line-1">Maximum Performance. Maximum Range.</div>
  <div id="line-2">Available for Model S and Model X</div>
</div>
```

The next one is for the buttons, and here I'm going to use `<span>` tags inside `<a href>`, just to show that it's possible to do so.

```html
<div id="buttons">
  <a href="#">
    <span class="button">ORDER MODEL S</span>
  </a>

  <a href="#">
    <span class="button">ORDER MODEL X</span>
  </a>

  <a href="#">
    <span class="button">READ MORE</span>
  </a>
</div>
```

The last one is our footer. We'll have a nested `<div>` tag for links and the flag image. We'll have a class for all links for easier styling.

```html
<div id="footer">
  <div id="footer-links">
    <a class="footer-link" href="#">Tesla Motors &copy; 2016</a>
    <a class="footer-link" href="#">Privacy & Legal</a>
    <a class="footer-link" href="#">Contact</a>
    <a class="footer-link" href="#">Careers</a>
    <a class="footer-link" href="#">Forums</a>
    <a class="footer-link" href="#">Locations</a>
    <a class="footer-link" href="#">
      <img src="img/flag.gif" id="flag" alt="US Flag" />
    </a>
  </div>
</div>
```

I think that's the basic HTML structure.

If you look at the browser, you can see all our elements.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Tesla+Homepage+HTML+Structure/image3.png)

In the next guide, we'll style all of them.

##Project Solution: Customizing the Tesla Homepage Navigation Styles with CSS

In this solution guide we'll walk through how to customize the navigation header styles for the Tesla homepage project using CSS.

Now that our content is in place, let's start styling the elements.  As always, the first step is to create a stylesheet and link it to our HTML file. We'll test it out by having a black background for the entire page, so we know our link is working.
That's all working fine, so we can remove this tag.

To start off, I'm going to give a style for the entire `<html>` tag, not just the `<body>`. This is where we'll set our background image.  For this image, we want it to be centered both on the vertical and horizontal axis, we don't want it to be repeated and we want it fixed.

In the future, if you ever need to set an image for the entire website, this is the way to do it.

Next, to maintain the aspect ratio, we'll set the `background-size` to "cover". You'll have to do this separately for all browsers though.

Lastly, we'll set a single font family, namely, sans-serif, for the entire application.

```css
html {
  background: url('img/teslas.jpg') no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  font-family: sans-serif;
}
```

If you open it in the browser, you'll see that the image has taken up the entire web page, and this is good.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Customizing+the+Tesla+Homepage+Navigation+Styles+with+CSS/image1.png)

Moving on, we'll work on our `#container` style, which will be essentially for all the elements. Here, I want the entire content to be centered, so I'm setting a value of "auto" to the `margin`. We'll also hard-code width to 1300px. Let's not worry too much about responsiveness for now, rather we'll focus on the design only.  In fact, the actual Tesla homepage itself is not too responsive, so we'll probably let it be as it is.

Next, we'll reduce the size of the logo image to 150px. Also, we want it to float to the left, and the position should be absolute.  

```css
#container {
  margin: auto;
  width: 1300px;
}

#logo img {
  width: 150px;
  float: left;
  position: absolute;
}
```

The output looks a lot better now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Customizing+the+Tesla+Homepage+Navigation+Styles+with+CSS/image2.png)

The next thing we're going to work on is the left navigation bar.  We want this to float to the left as well, and we'll set a left margin too.

Likewise, we'll style the right navigation bar. We obviously don't want any float, but we need a big left margin. If you're wondering why we're hardcoding specific values, it's because we are working for a specific-width website. In the future guides, we'll talk about customization and responsiveness.

For now, the code is:

```css
#left-nav-buttons {
  float: left;
  margin-left: 205px;
}

#right-nav-buttons {
  margin-left: 805px;
}
```

If you look at the output, you'll see that the navigation bars are lining up nicely.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Customizing+the+Tesla+Homepage+Navigation+Styles+with+CSS/image3.png)

Finally, we'll style our links. We want this to be white without any kind of text decoration. Also, I think a small margin on the left would give some space between each link.

```css
.nav-button {
  color: white;
  text-decoration: none;
  margin-left: 25px;
}
```

If you refresh the browser, it looks a lot cleaner.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Customizing+the+Tesla+Homepage+Navigation+Styles+with+CSS/image+4.png)

##Project Solution: Implementing Content Styles and Buttons

This solution guides examines how to style the homepage content and buttons with CSS styles for the Tesla project.

Our styles are coming along nicely, and we'll continue to work on the center part of the page now.

Before we move on, I want to make a small change to the right navigation buttons. I want to keep the `font-size` to 0.8em.

That's done, and we'll start with styling our content.  I'm going to start off with a top margin of 25%, and setting a value of "auto" to `margin-left` and `margin-right` to keep our content centered.  We'll keep the width to about 50% of the container, and also add a small padding on all sides.

```css
#content {
  margin-top: 25%;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
  padding: 10px;
}
```

If you look at the output, you can see that the image got moved down and the entire area including the SVG images got scaled down.  This is because SVGs are treated more like `<div>` tags, rather than as actual images.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution%3A+Implementing+Content+Styles+and+Buttons/image1.png)

Next, we'll work on our `#banner`, where we'll set a value of "block" to the `display` attribute.  Then, we want it to be centered, so we'll set an "auto" value to the left and right margins.  Next, we'll shrink the width further.

```css
#content #banner {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 300px;
}
```

The output looks better now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution%3A+Implementing+Content+Styles+and+Buttons/image2.png)

Next, we'll get to the marketing content.  For this, we'll give a top margin, align all the text in the center and have white as the text color.

```css
#content #marketing-content {
  margin-top: 20px;
  text-align: center;
  color: white;
}
```

For `#line-1`, let's have a `font-size` of 1.5em, so it's visible on the page. We'll also have a small margin at the bottom.  For `#line-2`, we'll keep the font size a little smaller and there'll be no margins.

```css
#line-1 {
  font-size: 1.5em;
  margin-bottom: 10px;
}

#line-2 {
  font-size: 0.9em;
}
```

If you refresh the browser, I think it gives a lot better look and feel.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution%3A+Implementing+Content+Styles+and+Buttons/image3.png)

Next, we'll move to the buttons. For the buttons ID, we'll align the text to the center, and have a top margin of 40px.

```css
#buttons {
  text-align: center;
  margin-top: 40px;
}
```

For the button class, we'll add some left and right margin. Then, we'll add a background color of black and a text color white, along with a padding of 10px at the top and bottom, and 24px on the left and right.  Finally, we'll set a `max-width` of 30px and a border of 1px that is solid and transparent. If it looks weird, don't worry, as it'll make sense later.

```css
.button {
  margin-left: 20px;
  margin-right: 20px;
  background-color: black;
  color: white;
  padding: 10px 24px 10px 24px;
  max-width: 30px;
  border: 1px solid transparent;
}
```

The output looks like this now:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution%3A+Implementing+Content+Styles+and+Buttons/image4.png)

We're not done yet. Moving on, we'll style the links on buttons now. We'll have no text decoration, and a font size of 0.9em.

```css
.button a {
  text-decoration: none;
  font-size: 0.9em;
}
```

The output hasn't changed, and that's because I styled the class instead of the ID. So, it should be like this:

```css
#buttons a {
  text-decoration: none;
  font-size: 0.9em;
}
```

The text on the buttons look much better now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution%3A+Implementing+Content+Styles+and+Buttons/image5.png)

The next thing is the hover effect for buttons, for which we're going to have a solid white border.

```css
.button:hover {
  border: 1px solid white;
}
```

If you hover over the buttons on the browser now, it'll give a nice effect.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution%3A+Implementing+Content+Styles+and+Buttons/image6.png)

Let's go back to the solid transparent border that we put in our `.button` class. If you remove this line, you'll notice a jumping effect when you hover the buttons. This is because it's making room for the white border. When you insert the code back, there's no jumping effect because the border was already there, but it was transparent. In general, such jumps are considered a bad practice with CSS, and should be avoided. Remember, if you face such a situation in the future, the simple fix is to add a transparent border.

Let's do the footer in the next video.

##Project Solution: Styling the Footer of the Tesla Homepage

This solution guide examines how to integrate the styles for the Tesla homepage footer, including how to update the links styles to function like a secondary navigation bar located on the bottom of the page.

Moving on, we'll style our footer now.

If you go the HTML file, you'll see there are two `<div>` tag overlapping each other - one called "footer" and the other one "footer-links". We don't need both, so we can remove one.

If that's done, let's get on with our styling.  For a sticky footer, we need to set the `position` to absolute. To tell the browser that it needs to be right at the bottom, we have to give a value of zero to the `bottom` attribute. Let's set the width and height to 1300px and 30px respectively, and we'll align the text to center.

```css
#footer {
  position: absolute;
  bottom: 0;
  width: 1300px;
  height: 30px;
  text-align: center;
}
```

This code will move our links to the bottom.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Styling+the+Footer+of+the+Tesla+Homepage/image1.png)

Next, we'll work on the links. Let's change the color to white, remove all text decoration, add a left margin and have a font size of 0.8em.

```css
.footer-link {
  color: white;
  text-decoration: none;
  margin-left: 25px;
  font-size: .8em;
}
```

Lastly, we'll work on the flag. We'll keep the width really small, and I want to it to stick up a little bit, so let's set a negative value to the bottom margin.

```css
#flag {
  width: 20px;
  margin-bottom: -5px;
}
```

This looks really neat, and all links including the flag are clickable.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Styling+the+Footer+of+the+Tesla+Homepage/image2.png)

##Project Solution: Integrating Custom Fonts

This solution guide walks through how to find and implement a custom font into an application using HTML calls and CSS font family attributes.

In this video, we'll talk about bringing in a custom font and integrating it with our project.

I went through quite a few fonts, and the one I really like is called "Raleway".  There are many places where you can get it, but I'll pick it from Google fonts. Feel free to choose a font that you like, or use the same one - it's up to you.

In Google Fonts, look for a link called "Select this font", and this will open a window with the HTML code in it. Copy and paste it just above your `<link>` tag for stylesheet. This location is important because of the cascading nature of style sheets.

```html
<head>
  <title>Tesla Clone</title>
  <link href="https://fonts.googleapis.com/css?family=Raleway" rel="stylesheet">
  <link href="styles.css" rel="stylesheet">
</head>
```
In the `html` style, let's update the `font-family` to "Raleway", but we'll still keep sans-serif as the background font.

```css
html {
  background: url('img/teslas.jpg') no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  font-family: 'Raleway',sans-serif;
}
```

If you refresh the browser, you can see the updated font. It sure looks a lot better.

Next, we'll work on aligning the center buttons and the footer links.

##Project Solution: Final Project Fixes and Summary

This guide walks through the final project fixes and gives a final walk through of all the systems utilized in order to build out the Tesla homepage project.

This is the final guide for the Tesla project, and in this one, we'll fix the center buttons and footer links.

First, let's fix the footer as this is an easy one.  Right-click on the page and open it in Inspect mode. I'm showing you how to debug problems in a real application, instead of just going to the code and fixing it. If you click on the footer `<div>`, you'll see that it stretches a long way to the left, which means, it's not inside the right `<div>` container.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Final+Project+Fixes+and+Summary/image1.png)

To fix it, let's move the footer `<div>` completely,  and out of all `<div>` tags except the main one.

```html
<div id="footer">
          <div id="footer-links">
            <a class="footer-link" href="#">Tesla Motors &copy; 2016</a>

            <a class="footer-link" href="#">Privacy & Legal</a>

            <a class="footer-link" href="#">Contact</a>

            <a class="footer-link" href="#">Careers</a>

            <a class="footer-link" href="#">Forums</a>

            <a class="footer-link" href="#">Locations</a>

            <a class="footer-link" href="#">
              <img id="flag" src="img/flag.gif" alt="US Flag" />
            </a>
          </div>
        </div>
    </div>  
  </body>
```

If you refresh the browser now, you can see that our footer is centered in the middle of the page.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Final+Project+Fixes+and+Summary/image2.png)

Next, we'll move on to the buttons, and these maybe a little harder. If you open the Inspect window, everything will look perfectly fine. So, it may be hard to guess, and in such a case, it's best to go back to your HTML code to look for any mistakes.

Here, I had made a typo mistake and this is the cause of the error.  If you look closely, you'll see that the `<span>` tag is not closed, and this is what is causing the error. If you close the tags, you're output should be:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Tesla+Homepage+Project/Project+Solution+-+Final+Project+Fixes+and+Summary/image3.png)

This is why it's always a good idea to check your tags if you face a bug that doesn't have an obvious solution.

So, with that, our site looks great and is a perfect replica of the Tesla homepage.
