#Chapter 9 Project: Using Bootstrap and a Website Template to Design a Social Network

##Twitter Bootstrap + Social Network Project Overview and Instructions

In this guide I walk through the project that we're going to build along with instructions on how to work with the source files. This project is different than the other projects since it's too extensive to build completely from scratch. Instead we're going to follow a real world project build process where we work with outside libraries such as the Twitter Bootstrap framework and a design sent over from a UI designer. And we'll walk through each of the key components for building responsive HTML/CSS websites.

The final project of this course is a social network, where you're going to learn new processes and techniques. Also, this project is sure to give some extra weight to your portfolio.

In this project, we're going to create a social network called "DailySmarty". This web page is fully responsive, so it'll scale well to any sized screen.  

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Twitter+Bootstrap+%2B+Social+Network+Project+Overview+and+Instructions/image1.png)

For this project, I hired a designer to design the homepage for us as it is quite extensive.  This is why it's not like the projects we built earlier, as a similar approach would take us 30 to 40 hours to build a homepage like us. Instead, we'll focus on the high level topics that we haven't go into earlier, to give you an idea of what it takes to build a real world application like this.

To cut short on the time, we'll use pre-existing design frameworks like Bootstrap. Now, this is not a template that you can customize for your needs, rather it is a framework that gives us a set of components, so we can integrate them  in our project. This way, we don't have to spend time creating anything from scratch. In addition, it gives us a grid-like system, so we don't have to spend a ton of time aligning different components on the page.
In a real world design, this is the approach you'll take, as it is rare for a client to ask you to build all components from scratch. So, this would be a good place to learn how to handle such applications.

This is also why I'm not going to ask you try it first before looking at the solution. Rather, I'd say follow along, and see if it makes sense for you.

##Implementing Responsive Tags into the Head Tag

This guide walks through how to integrate responsive meta data components into the head tag to allow the website to render a different layout based on screen size.

To get started, go to the show notes and click on the repository link. This will give you a list of files that I've used including the images. You can choose to follow along or use different images, that's totally up to you.

First off, I'm going to create a filed called "index.html". Inside the main folder, there's a subfolder called "images" and inside that, a nested subfolder called "common".

There is a reason why I have two nested subdirectories.  In the "images" subdirectory, all the image files pertaining to this page will be stored, while in the "common " subdirectory, images that are common to all the web pages will be stored.

You can find images at "www.github.com/jordanhudgens/social-network-html-css".  This link will also have the finished code, and I wouldn't recommend copy-pasting everything. Instead, just copy the image files and create the html and css files with me.  Just make sure you have the same directory structure if you plan to follow along with me.

Next, we need Bootstrap. To get it, go to "www.getbootstrap.com", and click on a button called "Download Bootstrap". To use this, create a new directory called "Vendor" and copy all the bootstrap files to it.

If you're wondering why we're integrating styles from the beginning, it's because bootstrap is one of the design frameworks, and we're layering all our code on top of this framework.  In our earlier projects, I created the HTML structure and then styled it, but here, we're going to work on it from start to finish.

Let's get started with our skeleton structure - `<!DOCTYPE>`, `<html>`, <`head>`, `<title>`, and `<body>`. In the `<html>` tag, I'm going to set the language to English, and inside the `<head>` tag, we'll setup our meta-data.  We'll set our `charset` to "UTF-8", `http-equiv` to "X-UA-Compatible" to make our webpage a responsive one, and `content` to "IE-edge" to make it compliant with Windows-based systems.

Next, we're going to include more things to make our page responsive. For this, we're going to use an attribute called `viewport`

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Social Network HTML/CSS</title>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE-edge">
    <meta name="viewport" content="width-device-width, initial-scale=1">
  </head>
</html>
```

You can also put meta-data information like author, description, and keywords, but we're not going to worry about it here.

Next, let's integrate bootstrap . If you open the bootstrap folder, you'll see a few .css files. Though `bootstrap.css` has all the style code, it's recommended you use `bootstrap-theme.min.css` because it contains the same styles minus the white space. Since we're not going to edit any of the bootstrap styles it's sensible to use this option to decrease your file size.

To integrate bootstrap, the code is:

```html
<link href="vendor/bootstrap-3.3.2/css/bootstrap.min.css" rel="stylesheet">
```

Make sure you have all of this code in place before moving on.

We'll continue with the design in subsequent videos.

##Building the Social Network Navigation Bar

This solution guide examines how to implement a navigation bar into the social network project, including how to work with the Twitter Bootstrap grid system.

In this video, we're going to start putting different elements that we can see on the page.

As always, we'll start off with a main `<div>` tag that has a class called "grey2". There's going to be nothing inside this tag, but it's still going to be there in case we choose to add some more things in the future. Also, this tag will not be so empty when we define the style for our "grey2" class. This is a common design convention used by many designers.

Next, we're going to create the header with a couple of nested `<div>` tags. Let's have an ID called "header" for the first `<div>` and a class called "container" for the nested one. Now, bootstrap already has a class called "container", so we won't have to do much styling here.

Inside this nested `<div>`, we're going to have another `<div>` tag with a class called "row". This is also a built-in class from bootstrap, and it creates rows for us, inside which we can place our elements.

```html
<body>
  <div class="grey2"></div>

  <div id="header">
    <div class="container">
      <div class="row">

      </div>
    </div>
  </div>
</body>
```

Inside the "row" div, we're going to create another `<div>` called "grey". In this tag, our aim is to have a grey line, that we'll define in the style for this class.

Next, we'll build columns. Remember, this is a responsive website, so we'll  need columns that adjust based on the screen size.  To implement this, we'll have a `<a href>` link, and we'll define multiple classes for it. Some of these classes are already available in bootstrap, and others we'll have to build. To pass multiple classes, simply leave a space between classes, and pass them all together, like this:

```html
<div class="row">
        <div class="grey"></div>

        <a class="col-xs-3 pull-left" href="#"></a>
      </div>
```

Out of these three classes, we have to define the style only for "logo", and the other two come from bootstrap. Next, we're going to have a logo image.  Here, we're going to have two logo images - one is the regular size and the other is small. We're including both these logos because we want to have the small logo for mobile sites.

```html
<a class="col-xs-3 pull-left" href="#">
          <img src="images/common/logo.png" alt="Logo>"
          <img src="images/common/logo_small.png" alt="Logo>"
        </a>
```

If this looks weird, don't worry as I'll show you how to use it.

The class "col-xs-3" will take only the first three columns if the screen size is small.

After the image, we'll have our search bar for which we'll use a class called "col-xs-9". In general, bootstrap works on a grid that has 12 columns, so if we use the three columns for logo, the remaining nine columns will go for our search box and avatar.  We'll also use the "pull-left" class for this `<div>` tag. We'll nest another `<div>` inside this that'll use six columns, and inside of it again, we'll have a `<span>` tag which will have classes "icon" and "icon-search".  Within the `<span>` tag, let's have our `<input>` tag for the text box.

```html
<div class="col-xs-9 pull-left">
          <div class="col-xs-6 pull-left">
            <span class="icon icon-search"></span>
            <input type="text" placeholder="Search..."/>
          </div>
        </div>
```

The next thing we're going to have on our header is the avatar. For this, we'll have a `<div>` tag, with the "col-xs-3" class. If you see, we have three columns for our logo, six for our search box, and the last three for our avatar, for a total of 12 columns. The other classes that we'll use our "avatar" and "pull-right". As you may have guessed, we have to define the style for "avatar" class while the other one comes from bootstrap itself. Inside this `<div>`, we'll have a link, another `<div>`  of class "mask", and another image.

```html
<div class="col-xs-3 avatar pull-right">
            <a href="#">
              <div class="mask"></div>
              <img src="images/common/guest_image.png" alt="Avatar">
            </a>
          </div>
```

Let's see how it all looks on the browser.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Building+the+Social+Network+Navigation+Bar/image1.png)

A couple more things here. First, we'll have a text "Welcome Guest", and underneath this, we'll have a couple of links for log in and register.

```html
<div class="col-xs-3 avatar pull-right">
            <a href="#">
              <div class="mask"></div>
              <img src="images/common/guest_image.png" alt="Avatar">
            </a>
            <strong>Welcome Guest!</strong>
            <a href="#">Login</a> or
            <a href="#">Register</a>
          </div>
```
Lastly, we're going to use something called a clearfix div. If you see, we have different styles for our elements, and if you don't want them to carry over, we have to use this `<div>`. Go up two levels, create a `<div>` tag, and link it to a bootstrap class called "clearfix".

The complete code for our header is:

```html
<div id="header">
    <div class="container">
      <div class="row">
        <div class="grey"></div>

        <a class="col-xs-3 pull-left" href="#">
          <img src="images/common/logo.png" alt="Logo>"
          <img src="images/common/logo_small.png" alt="Logo>"
        </a>
        <div class="col-xs-9 pull-left">
          <div class="col-xs-6 pull-left">
            <span class="icon icon-search"></span>
            <input type="text" placeholder="Search..."/>
          </div>
          <div class="col-xs-3 avatar pull-right">
            <a href="#">
              <div class="mask"></div>
              <img src="images/common/guest_image.png" alt="Avatar">
            </a>
            <strong>Welcome Guest!</strong>
            <a href="#">Login</a> or
            <a href="#">Register</a>
          </div>
        </div>
      </div>
      <div clear="clearfix"></div>
    </div>
  </div>
```

I think that's about it for our header.  The output looks like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Building+the+Social+Network+Navigation+Bar/image2.png)

If you see, we haven't define any style, and yet we have a neat looking header. Though it needs some more polishing, we still have something out of the box jut by using bootstrap.

Next, we'll go out of our `<div>` tag, and create another `<div>` for our main content. We'll have an ID called "main-menu" and a class called "small". Inside this, let's create two more nested `<div>` tags

```html
<div id="main-menu" class="small">
            <div class="container">
                <div class="row">
                </div>
            </div>
        </div>
```

We'll continue in the next video.

##Integrating Responsive Dropdowns with Bootstrap Components

This solution guide walks through how to integrate drop down components that are rendered differently based on the screen size viewing them.

Now that the header is ready, let's start adding content to the rest of the site.

Below everything, we're going to create another set of `<div>` tags that'll hold pretty much everything in the page.

As always, we'll have a "container" `<div>` and a "row" `<div>` inside of it. Within this, we're going to have another `<div>` tag for the 12-column grid. Along with this, we'll have a built-in class as well as a style that we'll create in the future.

```html
<div class="container">
  <div class="row">
    <div class="col-xs-9 article-grid pull-left">

    </div>
  </div>
</div>
```

Inside this nested `<div>`, we'll have a button with a link. Now, bootstrap offers many button styles, but it's not a good idea to use existing ones when you're building something for the production site. So, we'll override the default bootstrap styles just to give your own touch to it, and to make it look a little unique.

```html
<div class="col-xs-9 article-grid pull-left">
  <a href="#" class="btn btn-default btn-charcoal pull-left"></a>
</div>
```

In this code, the first two classes come from bootstrap while the third one, namely, "btn-charcoal" is a custom one.  Inside this, let's add a `<span>` tag and some text inside of it.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Integrating+Responsive+Dropdowns+with+Bootstrap+Components/image1.png)

The webpage looks like this now, though we'll style it better with our custom CSS class.

Next, we'll create an unordered list that'll have one from bootstrap, and the other that is a custom one. Inside this list, we'll place some list items.

```html
<div class="col-xs-9 article-grid pull-left">
  <a href="#accept-article" class="btn btn-default btn-charcoal pull-left"><span>Submit Article</span></a>
  <ul class="filter pull-right">
    <li>Top Now</li>
    <li>Most Recent</li>
    <li class="active">Today</li>
    <li>This Week</li>
    <li>All Time</li>
  </ul>
</div>
```
If you look at the code, you'll see that we have a special class for just one list item, and that is just to highlight it.

Next, we'll have the categories. Let's start with a `<a href>` tag and inside of it, a `<span>` tag.  This is going to have some built-in and custom button classes as well.

```html
<a href="#show-categories" class="btn btn-default btn-blue pull-right show-categories"><span>Categories</span></a>
```

On a side note, what we're doing here is practical learning - something that you're likely to do in the future. In general, while building websites, you're either given a page designed by someone else or a template, and from that, you'll have to build the site. In this sense, what we're doing now is not just going through or replicating code, but also giving you a hands-on feel of what you'll get from clients and how to take it from there.

Moving on, we'll have a select box that'll again have a mix of custom and built-in classes.

```html
<select data-class="filter-select pull-right blue filter-sort" name="type" class="filter-sort pull-right">
```

If you see, we have both `data-class` and regular `class` for our select boxes. Next, we'll put the same items from our unordered list, but instead of list items, we'll use the `<option>` tag.

```html
<a href="#show-categories" class="btn btn-default btn-blue pull-right show-categories"><span>Categories</span></a>
<select data-class="filter-select pull-right blue filter-sort" name="type" class="filter-sort pull-right">
  <option>Top Now</option>
  <option>Most Recent</option>
  <option selected="selected">Today</option>
  <option>This Week</option>
  <option>All Time</option>
</select>
```

If you're wondering about the `selected` attribute, it's a part of responsive design.  In a smaller screen, only these `<option>` items will be show, and the list-items will be hidden.

It's cool that you can accomplish something so complex with just bootstrap classes.

Let's continue in the next video.

##Customizing Content Headings

This solution guide examines how to integrate and customize the content headings for the Social Network homepage.

Our site is coming along good, and in this video, we're going to customize the content headings. In a responsive website, it's important to have the content headings displayed in different formats, so it can be customized to fit different screen sizes.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Customizing+Content+Headings/image1.png)

If you see, the categories listed on the right hand side are exactly the same values in the dropdown box. We'll use CSS to style them for different screen sizes.

That said, we'll continue building our content. Below the `<select>` box,  I'm going to paste a set of code, and we'll go through it line by line.

```html
<div class="clearfix"></div>

<div class="horizontal clearfix">
  <div class="col-xs-5 text">
    <h1>Business</h1>
    <h2>New Stuff Coming This Fall</h2>

    <p>Duis aute irure dolor in reprehenderit in
                            voluptate velit esse cillum <strong>dolore eu fugiat
                            nulla</strong> pariatur sunt in culpa qui officia
                            deserunt mollit anim id est laborum.
                            Duis aute irure dolor in reprehenderit...</p>

    <a href="article.html" class="btn btn-default btn-dotted pull-left"><span>Read More</span></a>
</div>
<div class="col-xs-7 image">
  <img src="images/image1.png" />
  <ul class="stats">
    <li>
      <span class="icon icon-view"></span>
      <p>369</p>
    </li>
    <li>
       <span class="icon icon-comment"></span>
       <p>36</p>
    </li>
    <li>
       <span class="icon icon-relations"></span>
       <p>52</p>
    </li>
    </ul>
    <div class="featured"></div>
  </div>
</div>
```

We're starting off with two `<div>` sections, the first one has the `clearfix` class as we're going to start off in a new line. Though we're nested within the same `row` class, we're on a different line, and this is why we're using this class. In the next `<div>` tag, we're again calling `clearfix` class and another custom one called `horizontal`. Inside this, we have another nested `<div>` that'll use the five columns of the bootstrap grid.  These five columns will contain text, while the remaining seven columns will be for an image related to that text.

The text has some styles, and there's also a link with styling that we've seen before.  The image also has some classes that are both custom and built-in.  An interesting thing is, there's an unordered list on top of the image, and this is not something you'll see often.  Though it looks crude on the webpage now, it'll eventually fall in place once we define the styles.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Customizing+Content+Headings/image2.png)

Before going further, I want to quickly talk about the grid system.  There are 12 columns that'll run from the left-most part of the page to the right-most. Inside this grid, you can have many nested grids.  If you look at our output, you'll see that the text and image are a part of the nested grid.
This is important to understand, especially if you're wondering why a 12-column grid is not spanning the entire page.  Also, if you look at the code, this text-image grid of 12 columns is nested inside a grid that takes nine columns, so the remaining three will be for listing out the categories.

Hope that's all clear now.

Moving on, I'll paste another block of content. If you're following along, you can either type out the content or simply copy it from the github repository.

```html
<div class="vertical">
  <div class="image">
    <img src="images/image2.png" />
    <ul class="stats">
      <li>
         <span class="icon icon-view"></span>
         <p>369</p>
      </li>
      <li>
         <span class="icon icon-comment"></span>
         <p>36</p>
      </li>
      <li>
         <span class="icon icon-relations"></span>
         <p>52</p>
       </li>
     </ul>
     <div class="featured"></div>
</div>
<div class="text">
    <h2>New Stuff Coming This Fall</h2>
    <p>Duis aute irure dolor in reprehenderit in
                                voluptate velit esse cillum <strong>dolore eu fugiat</strong>
                            nulla pariatur sunt in culpa qui officia
                            deserunt mollit anim id est laborum.
                            Duis aute irure dolor in reprehenderit...</p>
    <a href="article.html" class="btn btn-default btn-dotted pull-left"><span>Read More</span></a>
  </div>
</div>
```

This section begins with a `<div>` tag  with "vertical" class. It has an image and some stats that'll sit on top of the image once we integrate our custom style classes.  Lastly, it has some text, but it'll be located on the right hand side.

If you refresh the page, this is what you'll see.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Customizing+Content+Headings/image3.png)

If you see, the look and feel of this block is different from the previous one. Here, the text goes all the way to the right, but will change once we define our styles.

Moving on, we'll have another "vertical" class, which is a custom style. Along with this custom class, there are two others. There'll be an image and some text inside this `<div>` too.

```html
<div class="vertical padding featured">
  <div class="image">
    <img src="images/image3.png" />
    <ul class="stats">
      <li>
        <span class="icon icon-view"></span>
        <p>369</p>
      </li>
      <li>
        <span class="icon icon-comment"></span>
        <p>36</p>
      </li>
      <li>
        <span class="icon icon-relations"></span>
        <p>52</p>
      </li>
    </ul>
    <div class="featured"></div>
</div>
<div class="text">
    <h2>New Stuff Coming This Fall</h2>
    <p>Duis aute irure dolor in reprehenderit in
                            voluptate velit esse cillum dolore eu fugiat
                            nulla pariatur sunt in culpa <strong>qui officia
                            deserunt</strong> mollit anim id est laborum.
                            Duis aute irure dolor in reprehenderit...</p>
     <a href="article.html" class="btn btn-default btn-dotted pull-left"><span>Read More</span></a>
  </div>
</div>
```

If you come all the way down, you'll see some different classes for our button, and this is just to give it a different style.

The output looks like this now:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Customizing+Content+Headings/image4.png)

This section and the previous one are fairly similar, as the styles are almost identical.

The last part in this video is going to be a horizontal class.

```html
<div class="horizontal clearfix">
  <div class="col-xs-5 text">
    <h2 style="margin-top:0px;">New Stuff Coming This Fall</h2>

    <p>Duis aute irure dolor in reprehenderit in
                            voluptate velit esse cillum <strong>dolore eu fugiat
                            nulla</strong> pariatur sunt in culpa qui officia
                            deserunt mollit anim id est laborum.
                            Duis aute irure dolor in reprehenderit...</p>

    <a href="article.html" class="btn btn-default btn-dotted pull-left"><span>Read More</span></a>
</div>
<div class="col-xs-7 image">
    <img src="images/image4.png" />
    <ul class="stats">
      <li>
        <span class="icon icon-view"></span>
        <p>369</p>
      </li>
      <li>
        <span class="icon icon-comment"></span>
        <p>36</p>
      </li>
      <li>
        <span class="icon icon-relations"></span>
        <p>52</p>
      </li>
    </ul>
    <div class="featured"></div>
  </div>
</div>
```

Remember to nest it inside the right container if your copy-pasting the code.

If you see the webpage now, it'll have a different look and feel.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Customizing+Content+Headings/image5.png)

We'll continue adding content in the next video.

##Final Content Integrations for the Homepage

In this guide we'll walk through adding the final content items for the social network, spending specific time to analyzing how it works within the grid layout provided by Twitter Bootstrap.

I've added the rest of the content, and we'll go through it section by section. I pasted the content because I want you to focus on the different bootstrap classes and design integration, instead of seeing me type out everything manually.

The first thing I added is another `<div>` tag with "vertical" class.

```html
<div class="vertical padding featured">
  <div class="image">
    <img src="images/image2.png" />
    <ul class="stats">
      <li>
        <span class="icon icon-view"></span>
        <p>369</p>
      </li>
      <li>
        <span class="icon icon-comment"></span>
        <p>36</p>
      </li>
      <li>
        <span class="icon icon-relations"></span>
        <p>52</p>
      </li>
    </ul>
    <div class="featured"></div>
</div>
<div class="text">
   <h2>New Stuff Coming This Fall</h2>
   <p>Duis aute irure dolor in reprehenderit in
                            voluptate velit esse cillum dolore eu fugiat
                            nulla pariatur sunt in culpa <strong>qui officia
                            deserunt</strong> mollit anim id est laborum.
                            Duis aute irure dolor in reprehenderit...</p>
    <a href="article.html" class="btn btn-default btn-dotted pull-left"><span>Read More</span></a>
  </div>
</div>
```

It's similar to the ones we've done in the past, and includes an image and some text.

All these text-image combinations are located inside a `<div>` tag that has a column span of 9. We're now going to work on the remaining three column span. So, make sure you're out of that `<div>` before typing in this code.

```html
<div class="col-xs-3 sidebar pull-right">
  <ul>
    <li><a href="#">All</a></li>
    <li class="active"><a href="#">Business</a></li>
    <li><a href="#">Gaming</a></li>
    <li><a href="#">Leisure</a></li>
    <li><a href="#">Lifestyle</a></li>
    <li><a href="#">Offbeat</a></li>
    <li><a href="#">Politics</a></li>
    <li><a href="#">Science</a></li>
    <li><a href="#">Business</a></li>
    <li><a href="#">Gaming</a></li>
    <li><a href="#">Leisure</a></li>
    <li><a href="#">Lifestyle</a></li>
    <li><a href="#">Offbeat</a></li>
    <li><a href="#">Politics</a></li>
    <li><a href="#">Science</a></li>
    <li><a href="#">Business</a></li>
    <li><a href="#">Gaming</a></li>
    <li><a href="#">Leisure</a></li>
    <li><a href="#">Lifestyle</a></li>
    <li><a href="#">Offbeat</a></li>
    <li><a href="#">Politics</a></li>
    <li><a href="#">Science</a></li>
    <li><a href="#">Business</a></li>
    <li><a href="#">Gaming</a></li>
    <li><a href="#">Leisure</a></li>
    <li><a href="#">Lifestyle</a></li>
    <li><a href="#">Offbeat</a></li>
    <li><a href="#">Politics</a></li>
  </ul>
</div>
```

If you see, we're using the remaining three column spans for these links, so they will appear to the right of the text-image sets.  These are the categories placed inside an unordered list.

With this, our `<div>` tag with "container" class ends.

Finally, we have the "footer", that has another `<div>` tag with "container" class nested inside it.  

```html
<div id="footer" class="blue">
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <ul class="pull-left">
          <li><a href="index.html">Home</a>/</li>
          <li><a href="faq.html"  class="active">FAQ</a>/</li>
          <li><a  href="contact.html">Contact</a>/</li>
          <li><a href="affiliate.html">Affiliate</a>/</li>
          <li><a href="pricing.html">Pricing</a></li>
        </ul>
        <p class="copyright pull-right">Copyright © 2015 <strong>Daily Smarty.</strong> All rights reserved. </p>
      </div>
    </div>
  </div>
</div>
```

This contains an unordered list of links and our copyright image.

At the very end, I've added a line of JavaScript.

```html
<!-- Bootstrap -->
<script src="vendor/bootstrap-3.3.2/js/bootstrap.min.js"></script>
```

Don't worry too much about it, as you won't need it at all. I just put it in there to show you how you can give access to bootstrap classes through JavaScript.

There's one more piece of code I've added at the end.
They are commented for now, but you'll have to uncomment them if you're application is going to be run on older browsers.

```html
<!-- HTML5 Shim and Respond.js IE8 support of HTML5 elements and media queries -->
<!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
<!--[if lt IE 9]>
  <script src="vendor/bootstrap-3.3.2/js/html5shiv.js"></script>
  <script src="vendor/bootstrap-3.3.2/js/respond.min.js"></script>
<![endif]-->
```

After all this, the output looks like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Final+Content+Integrations+for+the+Homepage/image1.png)

If you see, that's quite a lot of content. it doesn't look great, though we've used many pre-built bootstrap classes. This is because bootstrap only provides a foundation for our page and doesn't give all the styles we need. This is why it's a bad design practice to only use bootstrap classes for design. You can use them, provided you also use some custom classes to give it a unique touch.

So, we'll get to styling them in the next few videos.

##Implementing CSS Styles

This solution guide walks through how to copy over the CSS styles for the social network, including how to organize the file structure and call the items from within the HTML file.

In this video, we're going to start styling our page. For the code, go to "www.github.com/jordanhudgens/social-network-html-css".

For styles, go to a file called "main.css". As you can see, this has almost 5000 lines of code, so I'm just going to copy  paste it, and we'll go through it. It would take an enormous amount of time for us to type it all out, this is why we're doing it this way.

Don't let such a long file intimidate you, as many of the classes will have overlapping styles.

So, let's get started! I'm going to create a folder called "css", and a subfolder called "common". Inside this, we're going to create a file called "main.css", and we'll paste all the code in this file.

First off, let's link CSS within our HTML file, below the bootstrap link because bootstrap is our foundation, and we want our CSS styles to be built on it.

```html
<link href="vendor/bootstrap-3.3.2/css/bootstrap.min.css" rel="stylesheet">
<link href="css/common/main.css" rel="stylesheet">
```

If you refresh the page, this is how it should look.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Implementing+CSS+Styles/image1.png)

If you see the buttons, they look a lot different from the default bootstrap buttons, and this is because we have overridden them with our custom styles.  Also, check for responsiveness by reducing the size of the page.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Implementing+CSS+Styles/image2.png)

I think it's pretty impressive, but we still have some work to do.

Before that though, let's walk through our CSS code. We obviously can't go through line by line because it's too much, and also much of it is what you already know.  So, we'll talk only about a few things here.

There are some styles that affect the entire page.

```css
* {
  outline: none;
}

html {
  height: 100%;
}

body {
  min-height: 100%;
}
```

We want the entire page to have a height of 100%, and want no outline.  The `a` links and pseudo classes also have no outline or text decoration.

```css
a {
  border-radius; 0px;
  text-decoration: none;
}

a:active, a:hover, a:focus {
  outline: none;
  text-decoration: none;
}
```

Next, we'll move on to something important. If you see the `.btn-default` class, you can see how we have overridden the default bootstrap class. You can even compare it to the `.btn-default` class located in `bootstrap.css`.

This is the default one in `bootstrap.css`

```css
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
```

Compare it with what we have in our CSS code.

```css
.btn-default {
  background: #0991A9;
  padding: 11px 35px;
  color: #fff;
  font-size: 14px;
  font-family: Museo-500, sans;
  border-radius: 0px;
  border: none;
}
```

We also have some custom buttons called `.btn-dotted`.

```
.btn-dotted {
  color: #666666;
  font-size: 14px;
  font-family:Museo-500, sans;
  text-transform: uppercase;
  height: 50px;
  text-align: center;
  background: none !important;
  border: 1px #989898 dotted;
  border-radius: 0px;
  margin-bottom: 109px;
```
You can't find this class in `bootstrap.css` because this is a custom class we've created for this page.

So, to override classes, you'll have to use the same class name, but inside it, you can define your own style.  

However, to do that, your link to stylesheet must be below that of the bootstrap, as the style is of a cascading nature.

If you reverse the code, the default style of bootstrap will not be overridden, so you'll see only the default style on the page.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Implementing+CSS+Styles/image3.png)

Can you see the difference in button styles? This is why it's called cascading stylesheet.

##Responsive Media Queries

In this guide we walk through how to use media queries in order to customize how a website responds when accessed by smartphones, tablets, and desktop browsers.

So far, we've talked about some important things like overriding default classes and using Bootstrap's grid system. In this guide, we're going to talk about responsiveness.

Bootstrap has a built-in class called "media" that allows us to build responsive websites. Also known as media query, this is what allows us to use different styles for different screen sizes. If you saw many different elements on the webpage, it was to customize them for different gadgets.

```
/* Mobile screens ------------- */
@media only screen and (max-width: 600px) {
  .btn-default {
    padding: 11px 15px;
  }

  #heading .avatar {
    width: 60%;
  }

  #header {
    padding-left: 20px;
    padding-right: 20px;
  }

  #header .avatar {
    overflow: hidden;
    width: 70px;
  }
```

If you look at this code, what it essentially says is these styles should be applied only when the media screen has a max-width of 600px or less, which translates to mostly mobile screens.  Note that the keyword here is `@media`.

See the changes here. For example, the `avatar` size is shrunk to 60%, and our header image is only 120px.  Another change is the `article-grid` class.

```css
<div class="article-grid">
div.article-grid {
  width: 100%;
  padding-left: 30px;
  padding-right: 30px;
}

div.article-grid .filter-sort {
  display: block;
  margin-bottom: 30px;
}

div.article-grid .filter-sort .options {
  width: 100%;
}
```

If you search for it in the `index.html` file, you can see that we've used it here:

```html
<div class="container">
  <div class="row">
    <div class="col-xs-9 article-grid pull-left">
      <a href="#accept-article" class="btn btn-default btn-charcoal pull-left"><span>Submit Article</span></a>
      <ul class="filter pull-right">
        <li>Top Now</li>
        <li>Most Recent</li>
        <li class="active">Today</li>
        <li>This Week</li>
        <li>All Time</li>
      </ul>
```

In a normal screen, our article took up only nine columns, but for mobile screens, it occupies the entire area. Still, there's a padding of 30px on both the right and left side just to make it look nice.

If you shrink the webpage on the browser to fit a mobile screen, you'll see that the articles occupy the entire space, and this is really cool!

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Responsive+Media+Queries/image1.png)

So, that's how a media query works for mobile screens.

0Next, let's see how it's implemented for tablets.

```
/* Tablet screens ------------ */
@media only screen and (min-width: 600px) and (max-width: 786) {
  #header {
    padding-left: 20px;
    padding-right: 20px;
  }
```

If you see, these styles are applicable only for screens that have a minimum width of 600px and a maximum of 768px.
If the screen is less than 600px, then the styles for mobile screens would apply. Here, the styles only have a slight change. The `avatar`, for example, is shrunk to 45% as opposed to 60% in mobile screens.  I'd suggest you go through this code to get a feel for it.

Next,  we'll see how the styles have changed for desktop screens that have a width of 768px to 1024px. The `avatar` here is only 35%.

```
/* Desktop screens ------------ */
@media only screen and (min-width: 768px) and (max-width: 1024px) {

  /* Common */

  #header .avatar {
    width: 35%;
  }

  /* Home */

  div.article-grid div.vertical {
    width: 46%;
  }
```

Finally, we can use `@media` to customize it for large screens, like this:

```
/* Large screens ------------ */
@media only screen and (min-width: 1024px) and (max-width: 1224px) {

  /* Common */
  #header .avatar {
    width: 30%;
  }

div.article -grid div.vertical {
  width: 47.5%;
}

div.login .mobile img,
div.order .mobile img,
div.login .mobile img {
  width: 30%;
}

div.billing .author {
  display: block;
  right: -250px;
}
```


Though the maximum width is set to 1224px, it doesn't mean the site won't work for larger screens. If you have to display your webpage on a really huge screen, you can modify the screen size for that too. If you see, the number of style changes is lesser than other screen sizes because there are not many changes you'll need to make here.

So, that's how you can use media queries to make your webpage more responsive.

##Bug Fixes

This guide walks through the final fixes for the code structure in order for all of the styles to work properly.

Before adding the final touches to our project, let's fix some of the issues we're currently seeing.

Firstly, we'll have to fix the double logo.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Bug+Fixes/image1.png)

If you see, our category links are all the way down, and not on the right side, and we'll have to fix this too.

Both these issues are related, so a common fix would work for both. Since we have a double logo, the second one pushes our content down, and this in turn, has moved the category links below the article.

To fix this issue, I went to `main.css` file, and started looking for a class called `.logo`. Then, I found that there were two logo classes, and this is what is causing the problem.

```
.logo {

    padding:29px 48px 30px 2px;

}

img.logo-small {

    width:59px !important;

    height:57px;

    position: absolute;

    top: 25px;

    left: 20px;

    display:none;

```

This class was not included in the html file, so to fix it, let's add this class here:

```html
<a class="col-xs-3 logo pull-left" href="#">
  <img src="images/common/logo.png" alt="Logo">
  <img class="logo-small" src="images/common/logo_small.png" alt="Logo">
</a>
```

Now, if you refresh the browser, everything should work fine.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Bug+Fixes/image2.png)

Let's see how it looks on a smartphone, and this is fine too.  Here, you can see the small logo alone.

So, how does this work? If you go to the `.logo-small` class, you'll see that it has a value of "none" for the `display` attribute.  So, it won't be displayed for a normal screen. But, when the size shrinks, the value of `display` will change to "block", in the `@media` code for mobile screens, while the regular logo's display would be changed to "none".
I think that's a cool implementation.

Before we end, there are a few small changes I want to make. The logo is getting a little stretched for mobile screens, so let's fix that by changing the image width and height.  Let's put a value of 50px for the `width`, and we'll get rid of the height attribute completely.

```css
img.logo-small {

    width:59px !important;

    position: absolute;

    top: 25px;

    left: 20px;

    display:none;

}
```

This looks a lot better now.

##Integrating Custom Fonts

This guide examines how to integrate custom fonts that are embedded within an application and how to call them from the CSS style files.

Now that our site is almost complete, I'm going to show you how to integrate custom fonts.

If you search for "fonts" in your CSS file, you'll see  a few different font families that have been used, like this one:

```css
#main-menu a span, #sub-menu a span {

    color:#FFFFFF;

    font-family:FrutigerLTStd-Light, sans;

    font-size:15px;

    height:45px;

    padding-top:10px;

    text-align:center;

    display:block;

}
```

All these custom fonts are available for you. Go to "www.github.com/jordanhudgens/social-network-htmls-css/blob/master/css/commons/fonts.css". This file lists out all the fonts, and also gives the link to each of these font types. It's important to note that all this information is available in the form of a CSS file. This is the best way to make a custom font available throughout the application and to store it locally. You can copy this code, and place it in a file called "fonts.css" in the "common" subfolder.

If you look at the code, you'll see that it has all the variations of a particular font - and this something you'll do in a professional grade application.

```css
@font-face {

    font-family: 'FrutigerLTStd-Light';

    src: url('fonts/FrutigerLTStd-Light.eot');

    src: url('fonts/FrutigerLTStd-Light.eot#iefix') format('embedded-opentype'),

        url('fonts/FrutigerLTStd-Light.woff') format('woff'),

        url('fonts/FrutigerLTStd-Light.ttf') format('truetype'),

        url('fonts/FrutigerLTStd-Light.svg#FrutigerLTStd-Light') format('svg');

}
```

We have also created some custom fonts, like this one:

```css
.Museo-500 {

    font-family: "Museo-500";

    font-weight: normal;

    font-style: normal;

}

.Museo-300 {

    font-family: "Museo-300";

    font-weight: normal;

    font-style: normal;

}

.FrutigerLTStd-Light {

    font-family: "FrutigerLTStd-Light";

    font-weight: normal;

    font-style: normal;

}
```

If you go back to the `main.css` file, you can see that the font families are nothing but custom classes that were created.  I think this is a nice way to organize your fonts, though you don't necessarily have to do it this way. You always have the choice to call a font directly from CDN.

If you go to github, you'll see a folder called "fonts" that has all the different font families. The best way to access them is to simply download them, put them in a folder called "fonts" inside the "common" subfolder, and you'll be good to go.

If you're wondering how the `fonts` are integrated with the `main.css` file, it's because of this import.

```css
@import url('font.css');
```

The webpage looks like this now:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/Bootstrap+Project/Integrating+Custom+Fonts/image1.png)

So, that's how you can integrate custom font families.

##Favicon Integration and Social Network Summary

In this guide we'll walk through how to integrate a custom favicon into a website along with examining all of the tools we used to build the website.

In this final guide, we'll review the application, and add a favicon.

Favicon is the little icon or logo you see on the tab of your webpage, and they get downloaded to your system after you visit the webpage once.

I already have the favicon image in our github repository, so feel free to download it to your main application folder.

Next, go to `index.html`, and at the very bottom of the `<head>` tag, add a link to the favicon, like this:

```html
  <link rel="shortcut icon" type="image/png" href="favicon.png">
</head>
```

This should do the trick for you.

If you refresh the page, you can see a small logo on your tab.  With this, we're done with the application. Great job if you went through it. It was a professional application that I'm sure would have given you a feel of how to go about creating such projects for your clients in the future.

While working on professional applications, you'll be handed over a design like this made by a professional designer or a template, and you'll have to take it from there. This hands-on experience will help you then.

Feel free to use this code as a framework, and customize it the way you want.

With this, you're well on your way to become a professional HTML developer. As always, please let me know if you have any questions or feedback, and I'll be happy to answer them for you.

Good luck with everything!
