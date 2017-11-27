#Chapter 5 Project: Create the Google Homepage



##Google Homepage Project Overview and Instructions

This guide gives an overview of the project requirements, including instructions for how to build the Google homepage with HTML and CSS.

This is a fun section of the course, as now we're going to start building our project in HTML and CSS.

We are going to begin by replicating the Google homepage. If you see, this is a relatively simple webpage that combines a number of things that you already know such as working with images, creating buttons and text fields.

I'd strongly suggest you go to www.google.com, and try to replicate it yourself. This way, you learn better even if you struggle a little bit along the way.

That said, let's see what we're not going to build.  First off, we're not going to build the scrolling "I feel lucky" button. Instead, creating two regular buttons would be enough.  Next, we're not going to worry about the mic icon and the voice feature that it offers.  Also, we're not going to build the little icon set that you see at the top right side of the page.

So, we're going to build content in the middle of the page that includes a text field. This is not our custom text field, so we'll have to override it a little bit. Also, we're going to create two nice rounded buttons using custom CSS. Next, we are going to create a header that sits at the top right hand corner of the page, and a sticky footer that contains links to help users navigate from page to page.

So, try to do this on your own, and in the next few videos, we'll see what my implementations looks like. Good luck!



##Project Solution: Building the HTML Structure

In this guide you'll learn how to build out the Google homepage HTML structure, including adding the content and customizing the markup language.

I'm going to work on a Windows operating system for this project, just to show that the operating system doesn't matter when it comes to HTML coding.  It only has an impact for server-side code such as Ruby on Rails and other programming languages, and not for front-end programming.  To implement it on Windows, I'm using an editor called Visual Studio Code, but you can use anything that works for you.

To start off, I've created a directory called "Google", and inside this, I'm creating a file called "index.html".

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Building+the+HTML+Structure/image11.png)

In this file, we're going to start off with our basic HTML structure - `<!DOCtype>`, `<head></head>`, `<body></body>`.  Let's call the title of this page as "Google clone."  Much of our code is going to go inside our `<body>` tag.

If you switch back to the Google homepage, you'll see that it has three main components - header, content and footer.  To implement it, let's use custom tags inside our `<body>` tag.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Google Clone</title>
    </head>

    <body>
        <header>          
        </header>

        <div id="content">
        </div>

        <footer>

        </footer>
    </body>
</html>
```

If you open this file on your browser, there's nothing in it yet except the title.  However, if you right-click and choose "View page source" option, you'll see that it has all the code we've typed in so far.

Now, let's work on our header first. If you see there are three items, namely, Gmail, Images, and Sign in button on the Google homepage. To replicate this, we'll create an unordered list with an ID called "nav-right". Inside this list, we'll create three list items, like this:

```html
<body>
  <header>
    <ul id="nav-right">
      <li>Gmail</li>
       <li>Images</li>
        <li>Sign In</li>
    </ul>          
  </header>
```

If you open it in the browser, you'll see three list items. Though they are nowhere close to Google, it's a good starting point.



Next, we're going to create links to "Gmail" and "Images", and here, we're simply going to have a "#" as the value for  `<a href>` tag because we don't want it to go anywhere. Rather, we only want to create a hyperlink for now.  The third item is going to be a button, and we're going to use an `<input>`  tag for it.

```html
<body>
  <header>
    <ul id='nav-right'>
      <li><a href="#">Gmail</a></li>
      <li><a href="#">Images</a></li>
      <li><input type="button" id="sign-in" value="Sign In" /></li>
    </ul>         
  </header>
```

The output would be like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Building+the+HTML+Structure/image12.png)

Next, we'll move to the "content" section. Here, we'll create a `<div>` tag with an ID for the logo, but we'll not worry about bringing in the logo now. Then, we'll create another `<div>` tag for the search bar, and inside it have an `<input>` tag.

```html
<div id="content">
  <div id="logo">
  </div>

  <div id="search">
    <input id="search-box" type="text" name="search" />
  </div>
</div>
```
Next, we'll create a `<div>` tag for our search buttons, and create two `<input>` tags for buttons. I want to have a class for these buttons, so we can reuse the same style.  

```html
<div id="search-buttons">
  <input type="button" class="button" name="google" value="Google Search" />
  <input type="button" class="button" name="google" value="I'm Feeling Lucky'" />
</div>
```

Now, we'll move on to the last section.  For the footer, we are going to have two unordered lists - one for the right and one for the left.  We'll call the first one "footer-left", and have three list items called "Advertising", "Business", and "About".

We'll call the second list "footer-right", and have the following list items - "Privacy", "Terms" and "Settings".

The output will be:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Building+the+HTML+Structure/image13.png)

If you see, we have all the items we need. All that we have to do is some styling now.  Before we finish this video, let's quickly bring the Google logo. You can grab it from "https://github.com/rails-camp/html-css-devcamp/tree/master/google/img", as I'll give you access to this location, so you can download the `logo.png` file.  Alternately, you can copy the file or save it, create a subfolder called "img" inside your main "Google" directory, and paste this file inside it.

Now, include this image inside our `<div id = "logo">` tag.

```html
<div id="content">
  <div id="logo">
    <img src="img/logo.png" alt="Google Logo" width="350" />
  </div>
```

If you refresh your browser, you'll see this logo.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Building+the+HTML+Structure/image14.png)

So, everything is good now!



##Project Solution: Integrating the CSS Header and Content Styles

This lesson examines how the CSS header and content styles can be implemented in order to build out the navigation component for the Google homepage.

Now that we have all the content we want,  let's add some styling to it.

For that, we'll create a file called `styles.css`, and import it inside our `<head>` tag in `index.html`.

```html
<head>
  <title>Google Clone</title>
  <link rel="stylesheet" href="styles.css">
</head>
```

Just to make sure this file is working , I'll give a background color of black in our CSS file. If you refresh the browser, the background is black, and this means, everything is working fine.

Let's now get down to creating styles for the entire page.  First off, we'll create a * attribute, and this means, the style that we mention in the curly braces will apply to the entire page. For this project, let's set a margin of 0px, so it gives us flexibility to implement our sticky footer.

```css
* {
  margin: 0px;
}
```

Also, the nice thing about Visual Source is it gives you a detailed explanation for every attribute, and this is particularly good if you're just learning HTML or CSS.

Next, let's go to our `header` tag.  For our header, we want it to be on the top right side, so we have to set a value of 0px to our `top` and `right` attributes. Before that, we have to make the value of our `position` attribute as "absolute". Finally, we want our `text-align` to be to the right.

```css
header {
  postition: absolute;
  right: 0px;
  top: 0px;
  text-align: right;
}
```

If you refresh the page, you'll see that the header list has been moved to the top right position.  To remove the bullet points, we have to customize the `ul` and `li` tags.  First off, we'll change our `display` attribute to a value of "inline-block", so the values not one below the other, but on the side of each other.
Also, we'll add a margin of 10px between each item.

```css
header ul li {
  display: inline-block;
  margin: 10px;
}
```

If you refresh the browser, it looks much better.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Integrating+the+CSS+Header+and+Content+Styles/image1.png)

I think that's with the header.

We'll move to the content now. If you see the code, all the components are inside a `div` tag with an ID called "content".  This means, we are going to use a "#" sign for the style.  To start off, let's have a `margin` of 200px, and also use an attribute called `important`. It gives a good effect, and I'd recommend you play around with it a little bit to become familiar. Next, we'll center this content using the `flex` property, and justify it. Lastly, we'll set a value of "center" to our `align-items` attribute.

```css
#content {
  margin-top: 200px !important;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
```

The page now looks like this, which is closer to how we want.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Integrating+the+CSS+Header+and+Content+Styles/image2.png)

If you see, they're not stacked below the logo. To fix that, let's add a value "both" to an attribute called `clear` inside our `#logo` tag. Essentially, this attribute will allow us to have items on top of each other, instead of placing them from left to right. Also, we'll set the `width` to 100% and `text-align` to center.

```css
#logo {
  clear: both;
  width: 100%;
  text-align: center;
}
```

This should bring our page closer to the Google page.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Integrating+the+CSS+Header+and+Content+Styles/image3.png)

We'll have to do the same for our text field too, and we'll also add a top margin to give it some extra space.

```css
#search {
  clear: both;
  width: 100%;
  text-align: center;
  margin-top: 30px;
}
```

 Next, let's style our search box to make it longer. So, let's set the `width` to 600px, and `height` to 15px. We'll also give a custom border that is 1px thick, solid, and in gray color. Finally, let's add a `padding` of 5px and a `margin` of "0px, 0px, 5px, 0px".  Alternately, you can also do `margin-bottom`.

```css
#search-box {
  width: 600px;
  height: 15px;
  border: 1px solid #999999;
  padding: 5px;
  margin: 0px 0px 5px 0px;
}
```

Now, the output looks much closer to the original one.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Integrating+the+CSS+Header+and+Content+Styles/image4.png)

We'll continue styling in the next video.



##Project Solution: Building the Styles for the Buttons and Footer

This guide walks through how to create the styles for the Google homepage buttons and footer.

We'll continue from where we left off in the earlier video. I think our styling is coming along well, and is looking close to the Google homepage.

Moving on, we'll style the buttons now.

If you look at the Google homepage, the buttons are lighter and have rounded corners.  Go to `styles.css`, and define style for an ID called "search-buttons".

We'll have a value of "both" for the `clear` attribute, and give a margin on the top.  Next, for the `button` class, we'll round the corners by 2px,  and play around a little with the width and height. We'll also change the background color to a grayish white, and the font color to a charcoal color. If you see, I'm using a hexadecimal value for each color, and I picked these values from Photoshop. You can use any color editor you like to get the hexadecimal value of the color you want.  Then, we'll have a value of "relative" to the `position` attribute, so they are side to side.  We'll also change the `font-size` to 0.8em, and the `font-family` to "Arial".  We'll align the text to center, and increase the weight of the font to 600, to make it bold. Lastly, we'll have a margin of 5px on all sides except the top, and a `border` that is 0px thick, solid and white in color.

```css
#search-buttons {
  clear: both;
  margin-top: 30px;
}

.button {
  border-radius: 2px;
  width: 140px;
  height: 40px;
  background-color: #f3f3f3;
  color: #686363;
  position: relative;
  font-size: .80em;
  font-family: Arial;
  text-align: center;
  font-weight: 600;
  margin: 0px 5px 5px 5px;
  border: 0px solid white;
}
```

Let's see what this looks like on the browser.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Building+the+Styles+for+the+Buttons+and+Footer/image1.png)

I think it looks a lot similar to the Google homepage now.

We'll move to the footer now.

Let's start with a `position` of "absolute", and we'll have it on the left and bottom of the page, so both these attributes take a value of "0px". We'll have a 1px, solid and light gray border on the top, text aligned to the right, width 100%, background color of white, and the bottom margin to be set to 0px.

```css
footer {
  position: absolute;
  left: 0px;
  bottom: 0px;
  border-top: 1px solid #d1d1d1;
  text-align: right;
  width: 100%;
  background-color: white;
  margin-bottom: 0px;
}
```

Now, this alone doesn't do much, so we'll have to define more styles. Let's do it for the `ul` and `li` tags, like we did for the header.

```css
footer ul li {
  display: inline-block;
  margin: 10px;
}
```

Next, we'll work on the `footer-right` and `footer-left` IDs. For the latter, we'll define the `float` attribute to have a value "left", and for the former, we'll have the `float` attribute point to "right". Also, for `footer-right`, we'll have a margin on the right to a value of 30px.

```css
#footer-left {
  float: left;
}

#footer-right {
  float: right;
  margin-right: 30px;
}
```

If we check the browser now, it looks like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+Building+the+Styles+for+the+Buttons+and+Footer/image2.png)

And this is quite close to what we want.



##Project Solution: CSS Hover Effects for Links

In this guide you'll learn how to implement the CSS hover effects for the links on the Google homepage project.

Our layout is almost complete, and looks a lot like the Google homepage now. In this video, we'll look into customizing a few things like hover effects, font styles and links.

First off, if you see, the fonts used in the header are different, and they have different hover effects too, so we need to fix this. If you guessed we'll be using pseudo classes for this implementation, you're 100% right.

Open `styles.css`, and first, I'm going to add some comments for better readability.

Now, we'll add some pseudo classes for the links. Let's have the links in black color, reduce the font size a little bit, change the font family, and remove text decoration.

```css
header a:link {
  color: black;
  font-family: sans-serif;
  font-size: .8em;
  text-decoration: none;
}
```

The page should look like this now:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+CSS+Hover+Effects+for+Links/image1.png)

It's much closer to the Google page, and next, we'll add a hover effect.  In this pseudo class, we'll just add an underline effect.

```css
header a:hover {
  text-decoration: underline;
}
```

If you refresh the browser, you'll see the changes.

Next, we'll style the Sign-In button. The funny thing is this button is going to need the most styling out of all the elements we've worked on so far.

Let's get going. We'll have a border radius of 2px, a width of 80px and a height of 35px, change the background color to a shade of grayish blue and the font color to white, keep the font size to 0.8em to keep it the same as other elements on the header, have a relative position, align the text to center,  make it bold with a font weight of 600, and have a margin of 5px on all sides except the top. Lastly, our border will be 1px thick, solid, and a grayish white.

```css
#sign-in {
  border-radius: 2px;
  width: 80px;
  height: 35px;
  background-color: #2289d5;
  color: white;
  position: relative;
  font-size: .8em;
  text-align: center;
  font-weight: 600;
  margin: 0px 5px 5px 5px;
  border: 1px solid #CAC9C9;
}
```

Let's refresh the browser, and it should look like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+CSS+Hover+Effects+for+Links/image2.png)

If you see, this is much similar to the Google homepage.  You can also play with it a little bit in terms of color, font family, and anything else you want.  I'm happy though with these changes.

Then, we'll move on to the footer. Like the header, let's add pseudo classes.  However, let's have a color of gray, and the `list-type` to be none. The rest is the same as header.

```css
footer a:link {
  text-decoration: none;
  color: #787878;
  list-style-type: none;
  font-family: sans-serif;
  font-size: .8em;
}
```

I think the page now looks a lot more professional.

The hover effects will be the same as header.

```css
footer a:hover {
  text-decoration: underline;
}
```

As a last thing, we'll do hover effects for the two buttons located in the center of the page.

There are many styles you can add for the hover effect, but I want to keep it simple, and add a nice border to it. If you go to the style code of `.button`, you'll see that we added a border of white. In general though, it makes no sense to add a white border when the background is white, but it was done on purpose, so we can change the border color to a shade of gray for our hover effect.  Also, we'll change the cursor effect to a pointer.

```css
.button:hover {
  border: 1px solid #A6A6A6;
  cursor: pointer;
}
```

These changes look cool on the browser.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Google+Homepage+Project/Project+Solution+-+CSS+Hover+Effects+for+Links/image3.png)

We have a nice gray hover effect now. Try removing the white border from our `.button` style, and you'll see that the button looks a little ugly now.  This is why we have that border color, even if it sounds redundant.  With this, we're almost done with the site.



##Project Solution: JavaScript Auto Focus and Summary

This final video in the Google homepage project section walks through how to add a JavaScript auto focus solution and examines a summary of the project.

In this last guide for Project 1, we'll see how to add a cool auto-select feature. If you go the Google page, you'll see that it automatically puts the focus on the search box, so users can start typing into it directly. We're going to implement the same in our page too.

Before implementing it, I want to quickly increase the size of our input text field to about 25px.

Now for our auto-focus, there are many ways to do it, but the easiest way is to put some JavaScript in the header.  Since we've never used JavaScript before, I'm not going to talk about what it is in this tutorial. Rather, I'm only going to walk you through on what we can do to bring auto-focus using JavaScript.

Every time we want to use JavaScript, we have to use a tag called `<script>`, and mention it to be of type JavaScript.  Inside this tag, we'll create a small function called `focusIt()`.

```html
  <script type="text/javascript">
      function focusIt()
      {
        var my_search_box = document.getElementById("search-box");
        my_search_box.focus();
      }
      onload = focusIt;
   </script>
</header>
```

In this function, we're using a few built-in JavaScript methods to turn the focus on the `search-box`.
After this function, we're calling the `focusIt()` method every time the page loads. This code should give us the effect we want.

With this, we've successfully cloned the Google homepage. Hopefully, you've gained some hands-on experience with this project, and I also hope you can appreciate the different elements that go into creating a clean user-interface.
