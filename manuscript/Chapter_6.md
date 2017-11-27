#Chapter 6 Project: Create the Pinterest Homepage

##Pinterest Project Overview and Instructions

This guide describes the website that we'll be building, including a discussion of the tools to utilize and some recommendations on how to build out the project using HTML5, CSS3, and Font Awesome icons.

In this section, we're going to go through Project 2, which is to clone the Pinterest page.  We are going to do some things differently here because I want you to focus on the HTML and CSS elements that Pinterest uses, rather than worry too much about how the page looks.

The snapshot of what we're going to build is going to look like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Pinterest+Project+Overview+and+Instructions/final+product.png)

If you're thinking this is much different from Pinterest, you're right, and that's because I want to use this project to help you learn some important things in HTML design.

I'd like you to try and design this yourself before looking at the solution. One important thing to implement is the layout. If you see, each element is of a different size, and yet they all fit in well together inside the specified margins. In a sense, it looks like a puzzle, and each element is a piece of the puzzle.  Though it looks easy, it is not going to be easy to implement it.

Another important learning from this project should be to integrate icons on the page. This is something that you'll be doing a lot in your HTML projects, so it's good to know how to do it.  So, these are some of the things you should focus while building this page.

At this point in time, don't worry about responsiveness though, as we'll talk about it in later sections.

Good luck!

I'd recommend you watch the solution videos after you try your best with this project.

##Project Solution: Creating the HTML structure for the Pinterest homepage

This guide walks through the project solution for building the HTML structure and content for the Pinterest homepage.

In this video, we're going to start by building our basic HTML skeleton.  Let's create a file called `index.html` inside a folder called "Pinterest."  I also have five images including the Pinterest logo. To access these, go to "https://github.com/jordanhudgens/pinterest-html-css-clone". Here, you'll find a folder called "img" inside which I've put all the images you'll need for this project.

Let's get started with our basic tags - `<!DOCTYPE>`, `<html>`, `<head>`, `<title>` and `<body>` tags.  I'm calling this page "Pinterest Clone", but feel free to call it whatever you want.

Inside the `<body>` tag, we'll have different `<div>` sections.  If you look at the Pinterest page, you'll see a header that includes the logo, a search box, and three icons on the right. The next section is our content, also called wrapper. So, we'll have a separate `<div>` for each of these.

The basic skeleton is:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Pinteres Clone</title>
  </head>

  <body>
    <div id="header">
    </div>

    <div id="wrapper">

    </div>
  </body>
</html>
```

Similar to the Google project, we're going to start off with an unordered list for our header images.

First off, we'll put the Pinterest logo using the `<img>` tag, and the logo is located inside the "img" folder.

```html
<body>
    <div id="header">
      <ul>
        <div id="logo"><img src="img/logo.png" alt="logo" /></div>
      </ul>
    </div>
```

Next is the search box, which we'll create using our `<input>` tag.  You can use an ID or a class here, it's completely up to you.

```html
<div id="search">
  <input id="search-box" type="text" placeholder="Search" />
</div>
```
Next, we're going to put in our icons. For now though, we'll  have some placeholder content with links until we integrate our icons later.

```html
<div id="nav-buttons">
  <a href="#">Bars</a>
  <a href="#">User</a>
  <a href="#">Chat</a>
</div>
```

If you open this file on the browser, we'll have a logo, a search bar and three links.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Creating+the+HTML+structure+for+the+Pinterest+homepage/image1.png)

Though it doesn't look too nice, at least we have the elements we need up there.

For the body or wrapper section, we'll create a `<div>`, and a ton of nested `<div>` tags inside it.  We'll use a common class for all the nested `<div>` tags, for easier styling.  Inside each nested `<div>`, we'll have an image and some random code.

```html
<div id="wrapper">
  <div id="columns">
    <div class="pin">
      <img src="img/img_1.jpg"/>
      <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque</p>
    </div>
  </div>
</div>
```

You can see all this on the browser now. Next, we're going to bring in more images and text by simply replicating this nested `<div>` tag.  The only change will be the image and text.  We're changing the text because we want to know how to style items with varying amounts of text.  There are five images, and we'll duplicate them to have a total of 10 pairs of images and text.

In the real world though, you'll have a database query that pulls in images and content from a database to display it in the browser.  But, we won't worry about it for this project.

If you refresh the browser, you'll see all images and text, one below the other.

In the next few guides, we'll work on styles.

##Project Solution: Customizing the Navigation Header Styles with CSS

Walk through how to add the CSS styles for the navigation element for the Pinterest homepage project.

In this video, we're going to style our page, and the first step is to create a CSS file called `styles.css` inside a directory called CSS.

Next, we'll link it to our `index.html`.

```html
<link rel="stylesheet" href="css/styles.css">
```

As always, we'll test it by changing the background color to black. If you open the browser, you can see this change, so everything is working fine.

Let's get rid of this background color, and start with our header id. Since we did not use any custom tags, we'll just use our CSS selector.

For the header, let's have a width of 100%, background color of white, a color of gray, and finally a bottom margin of -20px.  Also, we'll have a border for the bottom, and a height of 55px.

```css
#header {
    width: 100%;
    background-color: white;
    color: #a1a1a1;
    margin-bottom: -20px;
    border-bottom: 1px solid #f4f4f4;
    height: 55px;
}
```

If you refresh the browser, you'll see a small header, but you still can't see any element because we haven't done any work on it yet.

Next, we'll work on our navigation items. As with the Google project, have the `list-style-type` value as none, `font-family` as Arial, a `font-size` of 0.8em, `font-weight` of  bold, and a `display` value as "inline-block".  This should give us the desired effect.

```css
#header ul li {
    list-style-type: none;
    font-family: Arial;
    font-size: .8em;
    font-weight: bold;
    display: inline-block;
}
```

Since there are going to be no text here, we won't work on attributes like `text-decoration`.

Next, we'll work on the logo. First off, I want to float it on the left. We also need to resize the logo, so we'll set the width attribute to about 35px, and will also use the float property to keep it to the left.

```css
#logo {
    float: left;
}

#logo img {
    width: 35px;
    float: left;
}
```

If you refresh the browser, you'll see the change.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Customizing+the+Navigation+Header+Styles+with+CSS/image1.png)

Moving on, we'll change the search bar.  Let's set the `width` to 50%, float this element to the left, a large margin of 240px on the left, and some extra padding on the top.

```css
#search {
    width: 50%;
    float: left;
    margin-left: 240px;
    padding-top: 10px;
}
```

We'll also work on the search-box a bit, by increasing its width and setting its height to 25px. Let's also add a `border-radius` of 8px and a padding of 10px on all sides. The background color for the search box is a dark gray, just like how it looks on the Pinterest page. Finally, we'll have a negative margin of 190px and  a border of 0px.

```css
#search-box {
    width: 150%;
    height: 25px;
    border-radius: 8px;
    padding: 10px;
    background-color: #e9e9e9;
    margin: -190px;
    border: 0px;
}
```

Finally, we'll do the navigation buttons. We want them to float right, and have some margin on the top and right.

```css
#nav-buttons {
    float: right;
    margin-top: 2px;
    margin-right: 20px;
    margin-left: 20px;
}
```

I think the output is getting us closer to the design we want.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Customizing+the+Navigation+Header+Styles+with+CSS/image2.png)

##Project Solution: Integrating Font Awesome for Website Icons

In this guide we'll walk through how to integrate the Font Awesome library in order to add icons to the Pinterest homepage website.

In this video, we're going to see how to integrate those cool header icons into our application.

Go to "www.bootstrapcdn.com/fontawesome/" , and you'll see a link and a dropdown arrow. Click on this arrow, and you'll get links for different front-end programming languages.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Integrating+Font+Awesome+for+Website+Icons/image1.png)

Copy the HTML link, and paste it in our HTML file, right below the stylesheet link.  Though nothing will change right away, it'll give us access to use different icon classes.

Next, go to "www.fontawesome.io" and click on an option called "icons" that is located in the navigation header. This will bring up a list of icons for you, and from this list, choose the ones you like. The good thing about these icons is they are fonts, and this makes them less buggy in programming. A decade ago, all icons were images, so there were always problems with rendering and resizing, but tools like Font Awesome have made it easier to work with icons.

From the list, click on the icon you want, and this should take you to the page that has the icon link. Copy this link and paste it in the `nav-buttons` id, like this:

```html
<div id="nav-buttons">
  <a href="#"><i class="fa fa-bars" aria-hidden="true"></i></a>
  <a href="#">User</a>
  <a href="#">Chat</a>
</div>
```

Likewise, do it for users and chat icons too.

```html
<div id="nav-buttons">
  <a href="#"><i class="fa fa-bars" aria-hidden="true"></i></a>
  <a href="#"><i class="fa fa-user" aria-hidden="true"></i></a>
  <a href="#"><i class="fa fa-commenting" aria-hidden="true"></i></a>
</div>
```

The output looks like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Integrating+Font+Awesome+for+Website+Icons/image2.png)

Though they are not styled the way we want, the icons are nevertheless there.

##Project Solution: Styling Font Awesome Icons

In this solution guide we examine the steps needed for styling Font Awesome icons in the Pinterest homepage project.

In the last video, we added icons from Font Awesome, and in this one, we're going to style them.

Open the `styles.css` file and start building the style for `nav-buttons`. Let's choose a gray for the color, remove all text decorations, increase the font size to 1.9em to make it really big, and give plenty of margin space on the left.

```css
#nav-buttons a {
    color: #bababa;
    text-decoration: none;
    font-size: 1.9em;
    margin-left: 30px;
}
```

The output now looks close to the original Pinterest page.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Styling+Font+Awesome+Icons/image1.png)

Next, we need to add some hover effects. We'll change the color to black, every time a mouse hovers on the icon.

Before that, I want to quickly show you how to pick the exact color used by Pinterest. Go to their homepage, right click, and choose the "Inspect" option. If you click on the icon, you can see the styles used, and here you can get the exact hexadecimal value used for the color.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Styling+Font+Awesome+Icons/image2.png)

Let's paste the same code for our hover effects too.

```css
#nav-buttons a:hover {
    color: #5f5f5f;
}
```

This gives us the effect we want.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Styling+Font+Awesome+Icons/image3.png)

I think the headers look nice now.

##Project Solution: Styling Pinterest Pins

In this guide we will walk through how to style the Pinterest pins to allow them to fit into each other in a grid style format using CSS styles.

In this video, we're going to do the bulk of styling.

If you go to the Pinterest site, you'll see the pins are free-flowing and fit well within the page. This is exactly what we'll do with our site too.

As a first thing, we'll create a set of styles for our wrapper. We'll work on our width, which we'll leave at 90%. Let's also set a `max-width` and `min-width` so that the wrapper is always within a range of 800px to 1100px. Next, we'll set the margins to 50px on all sides, and also use the `auto` mode to ensure that everything is centered.

```css
#wrapper {
    width: 90%;
    max-width: 1100px;
    min-width: 800px;
    margin: 50px auto;
}
```

Next, we'll work on styling our images.  We'll start with the CSS selector `columns`, and inside this, we'll add the styling options for every browser too.

```css
#columns {
    -webkit-column-count: 3;
    -webkit-column-gap: 10px;
    -webkit-column-fill: auto;
    -moz-column-count: 3;
    -moz-column-gap: 10px;
    -moz-column-fill: auto;
    column-count: 3;
    column-gap: 10px;
    column-fill: auto;
}
```

This code is a good way to organize different columns on a page, and if you see the output, it's shaping up well.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Styling+Pinterest+Pins/Image+1.png)

Next, we'll define style for our class `pin`. If you remember, this is the class we're using for all the images.

To start off, we want it to be displayed as an "inline-block", so they're not stacked on top of each other. We'll set the background to a shade of white, and a border of solid white that is about 2px wide on all sides. Both these shades of white are slightly different to give a subtle distinction. Now, we're going to use an interesting attribute called `box-shadow`.

We'll set the values for this attribute to "0, 1px, 2px, and rgba (34, 25, 25, 0.4)". If you're wondering why we're using `rgba` instead of a hexadecimal value, it's because we want to give some transparency here.  The first three values stand for red, green and blue, and the fourth is for transparency.

Moving on, let's add some margin on the right and bottom. Then, we need something like a column break. For this again, we need to implement it separately for each browser, as this is specific to HTML5.

```css
.pin {
    display: inline-block;
    background: #FEFEFE;
    border: 2px solid #FAFAFA;
    box-shadow: 0 1px 2px rgba(34, 25, 25, 0.4);
    margin: 0px 2px 15px 0px;
    -webkit-column-break-inside: avoid;
    -moz-column-break-inside: avoid;
    column-break-inside: avoid;
```

We'll also add a padding of 15px on all sides, except the bottom where we'll have only 5px.
Then, I think adding a gradient will be nice, and yet again, this has to be done separately for each browser. Essentially, we want the gradients to be tilted at 45 degrees, and we want it to go from a shade of pure white to off-white.  Let's keep the `opacity` at 1, and finally the transition to two seconds.

```css
.pin {
    display: inline-block;
    background: #FEFEFE;
    border: 2px solid #FAFAFA;
    box-shadow: 0 1px 2px rgba(34, 25, 25, 0.4);
    margin: 0px 2px 15px 0px;
    -webkit-column-break-inside: avoid;
    -moz-column-break-inside: avoid;
    column-break-inside: avoid;
    padding: 15px 15px 5px 15px;
    background: -webkit-linear-gradient(45deg #FFF, #F9F9F9);
    opacity: 1;
    -webkit-transition: all .2s ease;
    -moz-transition: all .2s ease;
    -o-transition: all .2s ease;
    transition: all .2s ease;
}
```

I guess that's about everything we need for our pins.

Next, let's update the style for our images.

We'll set the `width` to 100%, and have a 1px thick border at the bottom  of every image.  I think some padding  and a margin at the bottom would be nice.

```css
.pin img {
    width: 100%;
    border-bottom: 1px solid #ccc;
    padding-bottom: 15px;
    margin-bottom: 5px;
}
```

Then, we need some styles for our paragraph tag too. We'll change the font size to be from 12px to 18px, family to be Arial, and a backup font value to be sans-serif.  The color will be black, and margins will be 0px.

```css
.pin p {
    font: 12px/18px Arial, sans-serif;
    color: #333;
    margin: 0;
}
```

Finally, we'll set the hover effects for our images.  For this, we'll set the `border-radius` to 20px, and let's also change the cursor to a pointer.

```css
.pin:hover {
    border-radius: 20px;
    cursor: pointer;
}
```

That's it! Let's see how it looks in the browser now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Styling+Pinterest+Pins/Image+2.png)

I think it looks great!

If you look at the images, it may look like we're using a break tag between the image and text, but in reality, this is nothing but a border that we've included at the bottom of every image.  This is a better way to implement because sometimes we may just have images without any text. In such a case, the break line is unnecessary, and can even look a little out of place. This is why we are accomplishing the same effect with a border, instead of using a break line.

##Project Solution: Pinterest Homepage Summary

This guide walks through a summary of the Pinterest homepage project and discusses the code elements that made the solution possible.

Now that we've built the solution, I want to give you some tips on how you can take it forward from here.

If you go to the Pinterest site, you'll see that it goes from edge to edge, whereas ours doesn't, and this is because we have hard-coded the width dimensions in our `wrapper` selector. To fix this, remove the `max-width` and `min-width` attributes, and change the `width` to 100%.

This is how the output looks now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Pinterest+Homepage+Summary/image1.png)

If you see, the images are too big, and don't look nice! We can increase the column size to 5 instead of 3 in our `#columns`, and this looks better.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Pinterest+Project/Project+Solution+-+Pinterest+Homepage+Summary/image2.png)

You can even duplicate these images a couple times more to get a total of 20 images, and it'll all look nice on the page.  You can play around with these options some more to get a better feel of it all.
