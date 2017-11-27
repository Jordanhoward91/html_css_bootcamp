#Chapter 2 Guide to CSS Styles

##Implementing Inline CSS Styles

This guide walks through how to use Inline CSS styles. This approach allows developers to add styles to a specific element on a web site. While this is an easy approach it's main purpose is for testing out styles, using inline CSS styles in a production application is considered a poor practice.

We are now starting our section on style sheets.

CSS stands for Cascading Style Sheets, and as the name suggests, these are files that give styling to your application.  There are three different ways of styling your application using CSS, and in this video, we are going to focus on what is called an inline style.

Inline styles are when you put the styling options within the same HTML file. This way, they are not in an external file or at the top, but they are right next to the element you're styling. This makes for easy readability.

However, inline styles are considered bad programming practice and are not used by professional developers. You can still use them though to understand different styling options. I typically use inline styling when I want to test how a particular style looks before I move it to a CSS file.

Now, let's see how we can do inline styling.

I'm going to remove the `<h1>` tag, and instead have a `<div>` tag.  Now, the heading looks like a regular paragraph, as this is how `<div>` tags are rendered by default. To style, this heading, give a space after the word "div", and add the word "style".  Follow it with double quotation marks, and inside of these marks, put the different styling choices you want like your font-size and color.

```html
<body>
  <div style="font-size: 2em; color: blue;">My Great Article</div>
```

If you look at the code, you'll see a colon right after the style type, and a semi-colon after the value. Both these are required for the browser to process them.  Without that, you'll run into errors, and won't be able to place other styles next to it.

The output reflects our new style.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Implementing+Inline+CSS+Styles+%23+490/image1.png)

Next, let's add a top margin, like this:

```html
<body>
  <div style="font-size: 2em; color: blue; margin-top: 50px;"
```

If you see, this moved the entire page down by 50 pixels because we are making a change to the topmost element on our page. So, naturally, everything was pushed down. If you dont want that, you can add another option called `position`, and give a value of "absolute" to it. What this will do is make a change only to the title, but will not move other elements down. By default, `position` is relative, so you'll have to mention it explicitly if you don't want other elements to get moved.

```html
<body>
  <div style="font-size: 2em; color: blue; margin-top: 50px; position: absolute;">My Great Article</div>
```

This will the output:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Implementing+Inline+CSS+Styles+%23+490/image2.png)

You obviously don't want to have such a messy page, but it's good to know the different options you have.

Hope this gives you an idea of inline styling. We can do the same to other elements in the page. Let's make some changes to the second paragraph. I want the background to be black, text color to be white and some padding around the entire paragraph.

```html
<div class="paragraph_two" style="background-color: black; color: white; padding: 20px;">
```

This will change the display to the image below.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Implementing+Inline+CSS+Styles+%23+490/image3.png)

With padding, you have many choices. You can add more on the sides, top or bottom, depending on how you want an element to look on the page. Now, I want to increase the padding on the sides, and to do that, the code is:

```html
<div class="paragraph_two" style="background-color: black; color: white; padding: 20px 40px 20px 40px;"
```

`Padding` takes in one or four different arguments. If you pass just one argument, all the four sides have the same amount of padding, and when you pass in four arguments, the first one is for the top, second for the right side, third for the bottom and fourth for the left side, respectively.  In a way, these values work like a clock.

The output is,

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Implementing+Inline+CSS+Styles+%23+490/image4.png)

As you can see, the sides have more padding than the top! You can play around with these values to get a better feel of it.

Now, what if you want to get more granular than this. Lets say, you want a particular style only for three words within a paragraph. You can use the `<span>` tag for selecting and apply the styles you want.

  ```html
  <div class="paragraph_two" style="background-color: black; color: white; padding: 20px;">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut <span style="color: red;">odit aut fugit</span>, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem.</div>
  ```

This style can be nested inside another inline style as well.

So, this is how you do inline styling in HTML.

##Using Embedded CSS Styles

Learn how to utilize embedded stylesheets to organize your styles in the same file as the HTML code. This is a helpful tool when building websites, however this is still considered a poor practice for production applications and should only be used for debugging and development.

In the last video, we talked about inline styles, and in this one, we're going to talk about embedded styles.

For this video, I've removed all the code except for a heading and a paragraph, just to make it easy to follow.

Embedded styling means they are not inline, but they are still embedded in the same HTML file.  Though in the real world, you'll mostly work only with external style sheets, it's still good to know this option.

For embedded styling, go to your `<head>` tag, and add a new tag called `<style>`.  Inside this opening and closing tag, let's add all the different styles we want like background color, font family, and font sizes. We have to select the section for which a particular style to be applied. To do this, mention a section and follow it with curly braces, like this:

```html
<style>
  body {
    background-color:  blue;
  }
  h1 {
    color:  white;
    font-family:  sans-serif;
    font-sizes:  2.5em;
  }
  p {
    padding:  42px;
    width:  300px;
    color:  red;
  }
</style>
```
These changes are reflected on our page now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Using+Embedded+CSS+Styles+%23+491/image1.png)

In general, it's a CSS practice to put the code in a single line, if you have only one item.  So, our code should look like this:

```html
<head>
  <title>Embedded CSS</title>

 <style>
    body { background-color: blue; }

    h1 {
      color: white;
      font-family: sans-serif;
      font-size: 2.5em;
    }

   p {
      padding: 42px;
      width: 300px;
      color: red;
   }
 </style>
</head>
```

In the next video, we'll talk about using external stylesheets.

##Using CSS Best Practices with External Stylesheets

This guide walks through how to use external CSS stylesheets to properly organize a website codebase. This includes a discussion on system and server paths to ensure that the HTML pages properly call the stylesheet.

In this video, we are going to see the right way for using CSS - and that is through external stylesheets.

So far, we've seen inline styles where you place the style within the content itself, and embedded styles, where you put the style on the top part of the same HTML file. Now, we're going to see about external stylesheets, and here, you'll have an external file that contains all the styles you need for the entire application.

This is the best way to do CSS, as you can avoid code repetition. Say, you have a homepage, and you put in all your styles as an embedded one. Now, if you want another page with a similar style, you'll have to copy and paste this code to the new page. Such a practice results in unnecessary code duplication. Also, making a change can be cumbersome, as you'll have to do in every page. To avoid these problems,  we use an external stylesheet.

Now, let's create a file called `styles.css` in the same folder where you have your HTML file.  Now, open both the files, and in your HTML file, create a `<link>` tag that'll link the CSS file to this HTML file. So, the code is

```
<link href = "styles.css"  rel = "stylesheet"  >
```

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Embedded CSS</title>
    <link href="styles.css" rel="stylesheet">
  </head>

  <body>
    <div>
      <h1>My Heading</h1>

      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </div>
  </body>

</html>
```

If you see, this code connects our CSS file to our HTML one, and we are explicitly saying that this is a CSS file, so the browser can process it accordingly. Here, we are simply mentioning the name of the file without giving its path because the CSS and HTML files are located in the same folder. If the CSS file is in a different folder, then we may have to give its relative file path. If you notice, we have no CSS code in our HTML file

Next, open your `styles.css` file, and type the embedded style code we had earlier.  You can also try different styles and options just to get familiar with it.
Test it in the browser, and everything should look good.

Now, all this is great for small applications. However, larger applications need many CSS files, so it makes sense to have it all grouped in a separate folder.  You can even have a subfolder and put all your CSS files in it.  If you do that, you should update the new path in HTML file.

```html
<html>
  <head>
    <title>Embedded CSS</title>
    <link href="css/styles.css" rel="stylesheet">
  </head>
```

Here, I've put my `styles.css` inside a subfolder called `CSS`.

If you've never worked with file paths, all that you're doing here is traversing through the file system to find the location where your CSS file is located.

Let's say you move your `styles.css` to another subfolder inside `CSS` and call it `custom`, then your path should be:

```html
<html>
  <head>
    <title>Embedded CSS</title>
    <link href="css/custom/styles.css" rel="stylesheet">
  </head>
```

So, that is how you can use external stylesheets, and for the rest of this course, we'll be using only this type of CSS file.

##How to Use CSS Selectors

Learn how to work with the various CSS selectors in this guide. This will give you the ability to target specific elements on a page to add custom styles.

Now that you know how to create CSS files and call different elements on the page, we are going to talk about using IDs and classes in CSS.

If you go back to our `styles.css` file, you'll see that we have different styles for different tags like body, paragraph and heading.  However, what happens when you want to have a particular style for only a specific paragraph, and not all paragraphs?

This is where IDs and classes come handy.  I'm going to remove all the content in `styles.css` file and start from scratch. Before that, let's add some IDs to our HTML elements.
For the `<h1>` tag, I'm going to add an ID called `page-title`, and for the `<p>` tag, I'm going to add a class called `content`.  I'm also going to create another paragraph and have the same class associated with it. If you remember, our ID can be used only once in the page, whereas class can be used any number of times.

Next, I'm going to create a `<div>` tag, and nest the `<h1>` tag inside it. This `<div>` tag has an ID called "heading".  If you see, I use a tab to indent the nested content, and this helps with readability.  

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Embedded CSS</title>
    <link href="css/custom/styles.css" rel="stylesheet">
  </head>

  <body>
    <div id="heading">
      <h1 id="page-title">My Heading</h1>

      <p class="content">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>

      <p class="content">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </div>
  </body>

</html>
```

Now, go to `styles.css`. Again, if you remember, IDs have a "#" sign, so our code is:

```css
#heading {
  padding: 42px;
  background-color: #e8e8e8;
}

#page-title {
  font-family: sans-serif;
  color: #ab3939;
}
```

Here, I'm changing the background color of the `<div>` area to a light grey, and also adding some padding around it.   The `background-color` has a hexadecimal value, and this is the most popular way to represent a color, as it gives you an endless choice of colors. You don't have to memorize these values, as you can use a color picker tool to select the color you want, and it will generate the hexadecimal code for you.

For the `#page-title`, I want a different font and a nice dark red for the content.  So, this is how it looks on the browser.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Using+CSS+Best+Practices+with+External+Stylesheets+%23+492/image1.png)

Next, let's see how to style classes.

As I mentioned before, classes are represented by ".", so instead of the "#" sign, your classes should start with a "."

```css
.content {
  font-family: sans-serif;
  font-size: 0.8em;
  color: #ab3939;
}
```

Here, I'm changing the font family, reducing the font size. If you see,  I'm using a value of "0.8em" to reduce the size of the font. Typically, "1.0" is the default, so the value I'm using is relative to this default value. If I want to have a bigger size, then I'd choose "1.5em" or even "2.0em".  It's close to using a percentage but is a lot cleaner.

Now, the web page looks like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Using+CSS+Best+Practices+with+External+Stylesheets+%23+492/image2.png)

I hope this gives you an understanding of why we have IDs and classes, and how we can use it as our selectors.

Next,  I'm going to tell you about the cascading nature of these stylesheets. In general, cascading stylesheet means layers of styles that lay on top of each other. We can customize it in such a way that the styles at the end have the highest priority and will take precedence if there is a conflict.

In our example, notice how we have some duplicate content. The font-family and color are the same for both the heading and paragraph. In such a case, we can move this value to our `<body>` tag, as this pertains to the entire page.

```css
body {
  font-family: sans-serif;
  color: #ab3939;
}

#heading {
  padding: 42px;
  background-color: #e8e8e8;
}

#page-title {

}

.content {
  font-size: 0.8em;
}
```

Obviously, nothing changes on the browser.

The `<body>` tag's style is the root behavior and will apply to the entire page. If you want a specific style for only a part of your page, you can override this default behavior with custom style.  In our case, I want the `<p>` tag to have a smaller font, so I overrode the default value. You can even override the same styling element. For example, we have defined a red color for all the font in our `<body>` tag. Let's say, we want a charcoal color for our paragraph font, we can change it.

```css
body {
  font-family: sans-serif;
  color: #ab3939;
}

#heading {
  padding: 42px;
  background-color: #e8e8e8;
}

#page-title {

}

.content {
  font-size: 0.8em;
  color: #767676;
}
```

So, the web page looks like this now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Using+CSS+Best+Practices+with+External+Stylesheets+%23+492/image3.png)

You can get as granular as you want, and apply a specific style to any particular element in your page.  This is why we call it cascading stylesheets.

So, that is how we can use selectors in HTML and CSS, and apply specific style to them.

##Using CSS Animations

Learn how to use the powerful Webkit animation library to add animated background colors to HTML div elements on a page. I also discuss the design best practices associated with when to use this approach.

Now that you know CSS styles and selectors, let's see what more we can do with them. In fact, you can do some cool things like animations with CSS and HTML, and that's what we're going to talk about in this video.  

Before we being, let me tell you that animations can sometimes be annoying to users, so it's best to avoid too much of it in any website. At the same time, animations can be a powerful tool to grab the attention of users, provided they are used sparingly and in the right context.

So, now let's see how to do animations. Open `styles.css`, and go to the `#heading` tag. Add an attribute called `webkit-animation`, and it'll come with its own options. Let's play around with these options a little. I want this to run infinitely, and at an interval of five seconds. So, this is the code:

```css
#heading {
  padding: 42px;
  background-color: #e8e8e8;
  -webkit-animation: myAnimation 5s infinite;
}
```

Nothing will change in the browser because I haven't defined my variables yet. So, let's do that. I'm going to add another attribute called `animation` and give it the exact same value as the earlier one.

```css
#heading {
  padding: 42px;
  background-color: #e8e8e8;
  -webkit-animation: myAnimation 5s infinite;
  animation: myAnimation 5s infinite;
}
```

Next, I'm going to use a tool called `@-webkit-keyframes` and here, I'm simply passing `myAnimation` as a parameter.  Here is where we'll define our animation.  I want the background color to change to `#d3d3d3` at 50% speed.

```css
@-webkit-keyframes 'myAnimation' {
  50% {
    background-color: #d3d3d3;
  }
}
```

Lastly, we'll add something called a `@ keyframe`. This will also have the same name, and will have the same code as `@-webkit-keyframes`. The complete code looks like this:

```css
#heading {
  padding: 42px;
  background-color: #e8e8e8;
  -webkit-animation: myAnimation 5s infinite;
  animation: myAnimation 5s infinite;
}

@-webkit-keyframes 'myAnimation' {
  50% {
    background-color: #d3d3d3;
  }
}

@keyframes 'myAnimation' {
  50% {
    background-color: #d3d3d3;
  }
}
```

Refresh the web page, and you can see the color fading from dark grey to light grey, and that's really cool. If you can't see it clearly, try changing the background color to something bright, though I won't recommend such a color in a real-time application.

You can try this animation with other attributes such as text, padding and just about anything else you like. Just a note here - you need CSS 3.0 or higher or animations to work.

##How to Add a Background Image to a Website

This guide walks through how to add a background image to a website using the CSS background attribute.

So far, we've learned how to lay a background color and do animations with it. In this video, we're going to see how we can add a background image to a website.

Open `styles.css` and let's have an image as the background for the entire page. Go to `body` tag, and type this,

```
background: url('../../img/teslas.jpg');
```

If you notice, the URL option contains the exact path using which we can traverse to the image we want.  We're using the `..` option to move back one directory, so we can get to the image we want.  This URL will obviously change depending on where you've kept your image files, but just remember that you have to use two dots to move up one directory.

![medium](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Add+a+Background+Image+to+a+Website+%23+495/image1.png)

Though this image is good, we need to resize it a little bit because this image is all about cars and we can't see any of it!

So, let's say `no-repeat` as we don't want a tiled wallpaper-like image, and we'll move it to the center. The code is:

```css
body {
  font-family: sans-serif;
  color: #ab3939;
  background: url('.../.../img/teslas.jpg') no-repeat center center fixed;
}
```

So, the webpage now looks like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Add+a+Background+Image+to+a+Website+%23+495/image2.png)

We can see the cars now.

Let's also shrink it further. We can do that with the code:

```
webkit-background-size: cover;
```

This works for chrome and safari, but we'll have to fix it for Mozilla too, and for that:

```
-moz-background-size: cover;
```

We'll also have the default `background-size: cover;`

```css
body {
  font-family: sans-serif;
  color: #ab3939;
  background: url('.../.../img/teslas.jpg') no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  background-size: cover;
}
```

So, this code makes our image look a lot better.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Add+a+Background+Image+to+a+Website+%23+495/image3.png)

If you're wondering what `cover` is, it essentially tells the browser to shrink the image without changing the aspect ratio.

So, now you know how to grab an image and how to use it as a backdrop for a web page.

##Resources

- [Tesla Image] (https://commons.wikimedia.org/wiki/File:Five_Tesla_Model_S_electric_cars_in_Norway.jpg)

##Adding CSS Border Styles to HTML Elements

In this guide we'll walk through how to add custom border elements to HTML page elements, including how to give a custom look and feel to elements in addition to working with standard border styling.

In this video, we are going to learn how to work with borders in our application.

In general, border means a set of lines around an element to highlight it. But, if you're working with CSS, you can leverage borders to create some beautiful web pages.

So, we'll start by using some basic borders.

Open `styles.css`, and go to `#heading` tag. Add a simple border that is one pixel thick, black color and comes with solid lines.

 ```css
#heading {
  padding: 42px;
  background-color: #e8e8e8;
  border: 1px solid #333;
}
```

You can play around with these options. Make the border thicker or change the color. Like here, I changed the border size to 10 pixels and color to white.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Adding+CSS+Border+Styles+to+HTML+Elements+%23+496/iimage1.png)

Though there is no point in having a white border, I just wanted to show you how to change these options.

Now, let's change the content a little bit because I can barely read it.  Go to `.content` tag. add a background color that is the same as the heading.  Also, add a padding of 20 pixels all around and a border only on the left-hand side.  The code is:

```css
.content {
  font-size: 0.8em;
  color: #767676;
  background-color: #e8e8e8;
  padding: 20px;
  border-left: 10px solid #ab3939;
}
```

If you see the web page, it almost looks like a custom element. But, in reality, we just added some styles to an existing element.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Adding+CSS+Border+Styles+to+HTML+Elements+%23+496/image2.png)

Likewise, we can also have a border on the right and at the bottom to give a cupping-like feel to the paragraph.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Adding+CSS+Border+Styles+to+HTML+Elements+%23+496/image3.png)

I think that's pretty cool!

##Rounding Div Corners with Border Radius Styles

In this guide we'll walk through how to use the border radius style element to give divs rounded corners, including using an online tool that gives an instant preview and automated code snippets.

In this video, we're going to talk about the border-radius style.

If you look at our webpage, the design is ok. But personally, I don't like the straight lines and corners. Rather, I'd prefer to have rounded edges as I think it gives a neat look for our borders, and this is what we're going to implement in this session.

Before that, go to "www.border-radius.com". This free service allows you to experiment with different border values, so you can find the right design you like.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Rounding+Div+Corners+with+Border+Radius+Styles+%23+497/image1.png)

I'd suggest you experiment with the different values, just to get a feel of what it looks like. Once you've decided on the style you like, copy the code and paste it inside the appropriate tag in your CSS file.

In our case, I think a value of 3 is enough, so I'm going to copy this code. Before I paste it, let's create another element on our HTML page for our subheading. For this, I've created a `<div>` tag, and a `<h3>` for my subheading. So, this is the code:

```html
<div id="sub">
  <h3>My Subheading</h3>
</div>
```

Now, let's go to `styles.css` and define the style for `sub`. First, I'm going to give a background color that matches the rest of the content, and then paste the code we copied earlier from "www.border-radius.com".  I'm also going to do some padding and margins.

So, this is the code:

```css
#sub {
  background-color: #e8e8e8;
  margin-top: 10px;
  padding: 5px;
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  border-radius: 3px;
}
```

And the web page looks like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Rounding+Div+Corners+with+Border+Radius+Styles+%23+497/image2.png)

If you see, our subheading has rounded edges while the other elements have straight edges. In a real world application, you shouldn't have such conflicting styles. So, I'm going to paste the code for rounded edges to other elements too.

Also, I'd like to align all my headings at the same level, so let's add some padding to the `sub` element. Our left padding alone should be equal to 42px, which is what we've given for our previous heading. The rest of the sides can be just 5px.

```css
#sub {
  background-color: #e8e8e8;
  margin-top: 10px;
  padding: 5px 5px 5px 42px;
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  border-radius: 3px;
}
```

I think the webpage looks neat now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Rounding+Div+Corners+with+Border+Radius+Styles+%23+497/image3.png)

Now, we know more about a great tool called border-radius, and we've implemented rounded edges in our application.

## Resources

- [Border-Radius Generator](http://border-radius.com/)

##Customizing Height and Width Attributes in CSS

This guide explains how to customize the height and width properties of div elements using custom CSS styles.

In this video, we're going to be talking about sizes.  So far, we've let every element go all the way from left to right. But in the real world, this rarely happens as you want every element to occupy only a maximum width and height on a page.

Open `styles.css` and come all the way down to the `#sub` tag. Here let's contain the width of this element to 300px.

```
width: 300px;
```

If you see, this shrinks our subheading.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Customizing+Height+and+Width+Attributes+in+CSS+%23+498/image1.png)

However, we are hardcoding a value here, and this ignores our padding on the right. So, it kind of looks ugly and out of place. In general, your `width` attribute will take priority and will ignore other attributes that conflict with it.

A better way would be to shrink it with a percentage value. Let's say, we give something like:

```
width: 50%;
```

This would shrink the value to what the browser considers 50%. The advantage with this option is the size of this element would be 50%, even if you resize the browser to fit a mobile screen.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Customizing+Height+and+Width+Attributes+in+CSS+%23+498/image2.png)

Now, when you say 50%, it takes this value before our padding. So, if you say 50% and have a padding of 100px, then the entire width would be more than 50%. This is an important consideration to keep in mind while deciding the value. This explains why our subheading element occupies slightly more than half the page width. So, to make it exactly half, I'm going to give a width of 40%.

Next, we'll see what happens with height. If you look at our heading, you'll see that it occupies quite some space, and this is because we've given a padding of 42px on all sides.

If we want to reduce the height, we can remove the padding and simply have a height attribute.

```
height: 200px;
```

However, what would happen is our text would be right at the top, and we'll have to work on aligning it.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Customizing+Height+and+Width+Attributes+in+CSS+%23+498/image3.png)

This isn't so nice, so I'm bringing back our padding. Nevertheless, it's good to know your options.

So, this is how you can use height and width in CSS.  

##How to Implement Custom Fonts in HTML and CSS

This guide explains how to integrate custom fonts into an HTML document and then call the fonts from within the CSS files.

This is going to be a fun video, as we're going to talk about having custom fonts. These fonts give a nice look and feel to your webpage, and makes it unique too.

In this video, we are going to implement custom fonts with CDNs. These CDNs are nothing but an outside service from which we'll take different fonts. We'll also see a little about backup fonts that your browser will be able to render if there's any problem with the main font. These background fonts, in general, should look similar to your main font.

Let's start by going to "www.fonts.google.com". Here, you'll have plenty of fonts, so choose the one you like.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Implement+Custom+Fonts+in+HTML+and+CSS+%23+499/image1.png)

You can also type the name of a font if you know it, or you can search based on different categories.  You can also customize it with some options on your right-hand side. I think this list is pretty exhaustive, so make an appropriate pick.

I like a font called "Montserrat", but feel free to play with different font sizes and types.

When you select a font, you'll get access to its code, so copy it.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Implement+Custom+Fonts+in+HTML+and+CSS+%23+499/image2.png)

I'm going to paste this code in our HTML file, just above the link to our CSS file. Now, I'm placing it above because I want this to be called first. Next, copy the CSS code, and paste it in the `body` tag. If you notice, we already have a `font-family`, so just replace it with this code.

The entire webpage now has the new font.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Implement+Custom+Fonts+in+HTML+and+CSS+%23+499/image3.png)

Sometimes, you may not want this, as you'll want specific areas of the code to have different fonts.  In such a case, put this code inside the appropriate tags. For example, if I want this font only for the heading, then I can say,

```css
h1 {
  font-family: 'Montserrat', sans-serif;
}
```

Likewise, we can try other fonts for other sections of our webpage. Just remember to paste both the HTML code and CSS code. While pasting HTML code, you can put different font links in any order, but all of them have to be before the link to CSS file.

Now, even if I have a custom font, say something called "Raleway" in the `body` tag, the heading tag will continue to have only "Montserrat", as I've defined it separately for the `h1` tag.  Other areas still have "Raleway" though.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Implement+Custom+Fonts+in+HTML+and+CSS+%23+499/image4.png)

Now, if you look at our font code, we are asking the browser to display content in "Raleway" or "Montserrat". But sometimes, these fonts may not be available for a number of reasons, and in such a case, we're asking the browser to display everything in sans-serif. This problem would happen if a browser is not connected to the Internet, as this is the only way the browser is going to find these fonts.  In this sense, sans-serif is the backup font.  Since it looks similar to both "Raleway" and "Montserrat", it's not going to affect the user experience in any way.

So, this is how we can use custom fonts on our web page.

## Resources

- https://fonts.google.com

##How to Add Custom Font Styles in CSS

This guide gives a step by step guide for adding custom font style options in a CSS file to give the text in an HTML document a unique look and feel.

Now that you know how to create custom fonts, let's see how you can style fonts.

Open your HTML file, and let's start with a `<span>` tag for three words. Also, we'll create a class called `highlight` associated with it.  Next, we'll use the same class for another word in a different paragraph, something like this:

```html
<p class="content">
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse <span class="highlight">cillum</span> dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</p>

<p class="content">
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et <span class="highlight">dolore</span> magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</p>
```

Now, go to `styles.css`, and define the `.highlight` class.  As the name suggests, we're going to have some elements that'll highlight the words.

We're going to have a background color of yellow, and a font-weight of 600 to make it bold.  For the font-style, we can have italics just to highlight it better. Usually, I stop with these three attributes when I want to highlight fonts, but here, I'm going to show you all possible options, so you can make your own choices.

The next one is `font-variant` to which we can set a value called `small-caps`. As the name suggests, this will change the highlighted text to uppercase, and will also reduce its size when compared to the normal font size.  Another one is `text-transform` that would change all the letters to uppercase. Now, it makes no sense to have both these options, as they are essentially the same, but it's good to know your choices.

The code so far is:

```css
.highlight {
  background-color: yellow;
  font-weight: 600;
  font-style: italic;
  font-variant: small-caps;
  text-transform: uppercase;
}
```

Another option we have is `text-decoration` that can take options such as `underline`, `overline` and `line-through`. You can use all these three options together too, if you want.

The last one is `text-shadow`, that will give a shadow effect to the chosen words.  It takes four parameters - the first is the offset value for the x-axis, and the second is the offset value for the y-axis. The third value is the thickness of the shadow, while the fourth is the color you want for the shadow.

```css
.highlight {
  background-color: yellow;
  font-weight: 600;
  font-style: italic;
  font-variant: small-caps;
  text-transform: uppercase;
  text-decoration: underline line-through overline;
  text-shadow: 5px 0 1px #b02626;
}
```

So, that's how you can style your fonts using CSS.

##How to Properly Center Div Elements on a Page

This guide walks through one of the more challenging tasks presented to developers: centering divs on a page. In this lesson we'll examine the proper way to accomplish this task.

In this video, we're going to learn how to nest elements inside of other elements, and center those items.  This is one of the most frequently asked questions on the HTML/CSS side, so I thought I'd clear it up for you.

Though it's easy to implement it using Bootstrap or Foundation, you may not always have access to it. So, let's see how to do it using our CSS tags.

We're going to learn to do this by creating three pricing tables below our paragraphs. Also, we're going to make these elements responsive, so they get aligned in a single line for mobile screens.

 Let's start off with a `<div>` tag, and give it an ID called `pricing-table`. Next, we're going to create three `<div>` tags inside of it - one for each package. Let's also associate a class called `package` with these `<div>` tags.

```html
<div id="pricing table">
  <div class="package">
    <h2>Package 1</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do</p>
    <p>9.99/m</p>
  </div>

  <div class="package">
    <h2>Package 2</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do</p>
    <p>19.99/m</p>
  </div>

  <div class="package">
    <h2>Package 3</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do</p>
    <p>49.99/m</p>
  </div>
</div>
```

If you see the webpage, they're all placed one below the other.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Properly+Center+Div+Elements+on+a+Page+%23+501/image1.png)

Let's now work on our `package` class. Go to `styles.css` and give a `background-color`. I want this color to match the rest of the website, so I'm giving it the red color we have for our heading and subheading.  Let's also give it a border-radius of 3px.  Next, we'll do a padding of 20px, and a margin of 50px.

So, the webpage looks like this now:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Properly+Center+Div+Elements+on+a+Page+%23+501/image2.png)

Let's continue with our styling. We'll add a `font-size` of `1.2 em`, and a cool border bottom of 10px, solid and green color.  Finally, we'll shrink each element to have a `width` of `200px`.

```css
.package {
  background-color: #e8e8e8;
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  border-radius: 3px;
  padding: 20px;
  margin: 50px;
  font-size: 1.2em;
  border-bottom: 10px, solid green;
  width: 200px;
}
```

Though all that looks fine, we want it right next to each other. Now, to put them side by side, let's start working on the parent `<div>` class that has an id called `pricing-table`.

Inside this selector, add an option called `display` and give it a value `flex`.  This option puts the tables right next to each other.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Properly+Center+Div+Elements+on+a+Page+%23+501/image3.png)

This is exactly what we want! But, we're not done yet.

Use another attribute called `flex-wrap` and give it a value `wrap`. Essentially, this allows our items to wrap to the next one.  This option comes handy when we want the screen to shrink down for smaller screens.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Properly+Center+Div+Elements+on+a+Page+%23+501/image4.png)

Next, I want to center all these items.  If you have a big screen, you'll see that the tables are aligned to the left like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/How+to+Properly+Center+Div+Elements+on+a+Page+%23+501/image5.png)

But, what we want is that these elements should be spread throughout the page.

To fix this, we'll use an option called `justify-content` and give it a value `center`. I'm also going to put one more attribute called `align-items` and give this also a `center` value. So, the complete code for `pricing-table` is:

```css
#pricing-table {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
```

Now, if you see, the items are centered, regardless of the size of the screen. For mobile phones, the items get stacked one below the other.

So, this is one of the best ways to center elements. It's a good idea to save this code, so you can use it when you're building your own applications in the future.

##Working with CSS Pseudo Class Selectors

In this lesson we will walk through CSS pseudo class selectors to implement custom styles based on stages of the user's interaction.

Pseudo-classes are an interesting feature in HTML and CSS. The best way to learn it is through links.

So, I'm going to create a `<a href>` link, and have it take us to "www.devcamp.com". So, you can see this link on the browser.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Working+with+CSS+Pseudo+Class+Selectors+%23+502/image1.png)

If you see, the link has a purple color to it, because that's the default color for a visited site. If you open this file in an incognito mode, you'll see a bright blue color.  Now, let's say you want to customize this color. This is where pseudo classes come handy.

Go to `styles.css` and create custom attributes for the `<a>` tag. You can do that by

``` css
a:link {
}
```
Inside this, we're going to change the default color to black.

Next, let's change the color of this link in its visited state. We have a purple now, but I'd like to change it to green.  For this, the code is:

```css
a:visited {
color: green;
}
```
If you refresh the browser now, you'll see that it's green.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Working+with+CSS+Pseudo+Class+Selectors+%23+502/image2.png)

Moving on, we can change the color of the link to our page's red color when the mouse hovers it. The code:

```css
a:hover {
color: #ab3939;
}
```
Lastly, let's have a color for the `active` class.

```css
a:active {
color: blue;
}
```
If you refresh, the color will be green to start with. It'll change to red when you hover over it, and blue when you click it.

The final code is:

```css
a:link {
  color: black;
}

a:visited {
  color: green;
}

a:hover {
  color: #ab3939;
}

a:active {
  color: blue;
}
```

Each of these states will vary depending on how the user is interacting with the webpage.

So, this is how you can work with pseudo-class selectors.

##Implementing Ease In Animations with CSS

This guide gives a step by step approach for implementing the CSS Ease In effect to alter the look and feel of page elements based on user interaction.

In the last video, we saw how we can customize styles for different link states. In this video, we're going to see how we can do the same thing for `<div>` tags.

Unlike links, we have only the hover state for `<div>` tags, as visited and active states make no sense here.

Let's get started now. We're going to do the hover effect for our `package` class. I usually like to put the pseudo class just under the main class.

In this `.package:hover`, I'm going to change the background color to green, and the color to green.  Lastly, I'm going to change the cursor type to a pointer. The code is:

```css
.package {
  background-color: #e8e8e8;
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  border-radius: 3px;
  padding: 20px;
  margin: 50px;
  font-size: 1.2em;
  border-bottom: 10px solid green;
  width: 200px;
}

.package:hover {
  background-color: green;
  color: white;
  cursor: pointer;
}
```

When you hover over an element, it changes to green.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Implementing+Ease+In+Animations+with+CSS+%23+503/image1.png)

One thing is the change is instant, and this can kind of make it look gaudy. So, we'll use CSS to make this transition smoother.  To do that, go to `.package` class, and add transition code. We want the transition to focus only on the background color, have a fade-in time of 500ms, have a style called ease-out and a fade-out time of one second.

```css
.package {
  transition: background-color 500ms ease-out 1s;
  background-color: #e8e8e8;
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  border-radius: 3px;
  padding: 20px;
  margin: 50px;
  font-size: 1.2em;
  border-bottom: 10px solid green;
  width: 200px;
}
```

Now, we'll have to include this behavior for all browsers - Chrome, Mozilla, Opera and IE.

```css
.package {
  -webkit-transition: background-color 500ms ease-out 1s;
  -moz-transition: background-color 500ms ease-out 1s;
  -o-transition: background-color 500ms ease-out 1s;
  transition: background-color 500ms ease-out 1s;
  background-color: #e8e8e8;
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  border-radius: 3px;
  padding: 20px;
  margin: 50px;
  font-size: 1.2em;
  border-bottom: 10px solid green;
  width: 200px;
}
```

If you refresh, you can see a nice fade-out effect, and the transition is smooth.

The above code is only for changing the background color. If you want the same effect for all your elements, you can simply change `background-color` to `all`. This will remove the white fade-in effect and will be just a mild transition to green.

##Customizing Bullet Points Using CSS

Learn how to change the look and feel of bullet points (ul items), including various styles that can be selected instead of the default disc option.

In this video, we are going to walk through how to customize bullet points.

First off, I'm going to start with a unordered list, represented by the tag `<ul>`.  I'm going to create a class for it called `content-bullets`, and some list items inside it. Next, open `styles.css`, and we'll define the style for our `content-bullets` selector.

As a first step, we'll create some padding on the left side, of about 40px.  Then, we'll use the `list-style` attribute, and choose square from its options. Next, we'll increase the `font-size` to 1.5em.

```css
.content-bullets {
  padding-left: 40px;
  font-size: 1.5em;
  list-style: square;
}
```

That's it. I think our bullets look neat now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Customizing+Bullet+Points+Using+CSS+%23+504/image1.png)

##Using the CSS Float Property to Align Page Elements

This guide examines how to utilize the float property. This style will let us align elements side by side on the page.

In this video, we're going to see how to use the float property to align elements properly.

As always, create a new `<div>` tag in your HTML file, and give it an id called `blocks`. Inside this, let's create three block elements.

```html
<div id='blocks'>
  <div class='block'></div>
  <div class='block'></div>
  <div class='block'></div>
  <div class='block'></div>
  <div class='block'></div>
</div>
```

At this point, let's not worry about the elements inside each `<div>` tag.  Next, open `styles.css` and we'll start defining the attribute for `#blocks`.

First off, we are setting the `position` attribute with the value `absolute`, just to ensure that our elements are below the pricing tables always.

Now, we'll work on the `block` class.  We'll start with height and width, and give a value of 140px and 250px respectively. Then, we'll give our red as the background color.

```css
#blocks {
  position: absolute;
}

.block {
  height: 140px;
  width: 250px;
  background-color: #ab3939;
}
```

This gives a block like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Using+the+CSS+Float+Property+to+Align+Page+Elements+%23+505/image1.png)

If you think that our block is really big, you're right! It's definitely more than 140px, and this is because all the three blocks are placed one below the other. What we want is to place them side-by-side, just like our pricing table. How do we do that?

To make it a little easier, we'll add a margin of 20px, so it looks like three small rectangular blocks.  Now, to place it on the side, we're going to use a property called `float`, like this:

```
float: left;
```

Essentially, this code ensures that every element floats to the left of the previous element. It also gives us some dynamic behavior. Let's say, we want to add two more `<div>` tags. They'll also be placed to the left of the previous ones.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Using+the+CSS+Float+Property+to+Align+Page+Elements+%23+505/image2.png)

If you see, we're not using the `flex-wrap` code that we used earlier for our `pricing-tables` because we don't want a fixed position. If you expand the browser, the blocks that we created will move to the side, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+CSS+Styles/Using+the+CSS+Float+Property+to+Align+Page+Elements+%23+505/image3.png)

So, if you want elements to be centered and in a fixed position, it's best to use `flex-wrap`.  On the other hand, if you're not too worried about being centered, then you can always use this `float` property.

This is how you can add some dynamic behavior in CSS when you're not too worried about having elements centered.  
