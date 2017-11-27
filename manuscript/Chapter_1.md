#Chapter 1 Guide to HTML

##Tools We'll Use in the Course

In this guide I walk through the tools that we'll use in this course, including a discussion on what IDEs and Text Editors are best for HTML/CSS Development. I also examine the Espresso editor that I will use for demonstration purposes.

Before we begin learning HTML and CSS, let us go through some of the tools that we'll be using for this course.

The tool I'll be using in this course is called Espresso, and it looks like this.

![](https://s3.amazonaws.com/rails-camp-tutorials/html/html-section/tools/Snip20170412_3.png)

I like this tool because it allows me to type in HTML code, and whenever I want to see how it looks in the browser, all that I have to do is click on the Preview icon in top left corner. This opens a browser and shows the real-time view of whatever I'm working on.  You also have the choice to keep your editor and browser side by side, so every time you make a change and hit save, the change is instantly visible in the browser.

![](https://s3.amazonaws.com/rails-camp-tutorials/html/html-section/tools/Snip20170412_5.png)

However, this is a paid tool, so I won't say you absolutely need it for this course.  A free option that I like is sublime text.  Here, you can create a HTML file, add code and save it to a particular location. To see it on the browser, open your HTML file on your browser.  This free option doesn't offer real-time editing though.  Every time you make a change, you'll have to refresh the browser to see your changes.

Besides these two tools, you can use other editors too such as Text Wrangler and Visual Studio, though I wouldn't recommend Visual Studio simply because it comes with a ton of built-ins that can be quite confusing.  Notepad ++ is a good choice too, if you're using PC. It completely depends on what you like and feel comfortable. During the rest of this course, I'll be doing HTML demos on Espresso, but feel free to pick your tool.

##Basic HTML Website Structure

This guide explains how to build a basic HTML website, including the HTML5 syntax that works with all modern browsers.

One of the first things you need to know is that HTML uses a tag-based system. These tags are what the browser looks for to display what you want to show.

One of the most basic HTML 5 skeleton you'll see is:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Site Title</title>
  </head>

  <body>
    <h1>Hi there again</h1>
  </body>
</html>
```

Just a quick note here. I'll make this structure and all code available to you in the show notes. What I typically do is push up all these files to a repository called github, and you can access it from there.

Now, going back to the code, the first thing you'll have to type is `<!DOCTYPE html>`. This has to be exactly this way with angle brackets, an exclamation mark and the letters "DOCTYPE" in uppercase and "html" in lowercase. When a browser opens a page, this is what it looks for. Once it sees this tag, it knows this is a HTML 5 file, and it will render it accordingly.

Next, you'll have to wrap your code in tags underneath that. We start off with `<html> `, and if you see right at the bottom, we close it off like this: ```</html> ``` In general, every opening tag needs a closing one, and your code can get distorted if you don't have matching opening and closing tags. If you see,  the closing tag is the same as the opening tag, except it has the symbol "/" just after the angle bracket.

Inside the ` <html>` tag, you can have a `<head>` and `<body>` tag, where you can put a whole lot of content in these two sections. We'll go in detail about each of these tags in the subsequent videos. For now, just remember that `<head>` contains all your meta-data, and `<body>` contains all the information you see on the browser.
Also, HTML doesn't recognize end of line characters, so you can have line breaks between different sections for better readability, and it won't change the content on your browser.

So, to recap, you start off with your declaration where you declare your `DOCTYPE`. Then, have an opening and closing `<html>`  tag to tell the browser that it has to process all the content inside these tags. Inside the `<html>` tags, you can have `<head>` and `<body>` tags that'll contain all your content.

##Working with the HTML Head Tag

This tutorial explains how to use the HTML <head> tag to encapsulate meta data that is processed by the browser, including the website title, SEO data, and encoding.

Now that we know the basic structure of a HTML document, let's dive into the `<head>` tag, and see what you can put in there.
Essentially, `<head>` tag is where you put all the meta-data for your page.

```html
<head>
  <meta charset="UTF-8">
  <title>title</title>
</head>
```
The first line defines the `charset` which is the character set you'll be using. In general, you'll use `UTF-8` for displaying English alphabets and characters. So, you won't have to change this at all, unless you're going to work on a website that displays Chinese or Korean symbols and alphabets.
The second line uses the `<title>` tag. This where you control the title of your web page.  Go to "google.com", and if you see, there is the word "Google" on the tab, and this comes from the `<title>` tag.

 ![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Title_tag.png)

Besides these two tags, you can put in pretty much anything that is a part of meta-data.  Some common things you can put include:
`<meta description>` -  This will describe your meta-data and this is something that search engines like Google look for while indexing.
`<meta keywords>` - This tag will contain all the relevant keywords associated with your web page, and this is also something that Google looks for.
`<meta author>` - This gives the name of the person creating the page.
There are two things to notice here. First, the meta tags don't have a closing tag, rather they have the entire content between the angle brackets. Second, these meta tags do not change the content on your browser, as they are mainly for search engine optimization.
So, if you're wondering where they go and what happens to them, open your file on the browser.  Right click on the page, and choose the "View page source" option.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/view_page_source.png)

If you see, this content is the same as the one you have on your file.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/html-file.png)

So, Google looks at this code, and not what is contained in the body - which is what you see.  You can a lot more content too  inside the `<head>` tag. I'll open one of my websites, right click on the page, and choose "view page source", and you can see that there are a ton of things here.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/jordans-website.png)

Most of the meta-data was generated dynamically by rails, but we can use them in our page too. If you see, the `meta`  tag can also have a `name` and a `content` section, like this:

```html
<head>
  <meta charset="UTF-8">
  <title>My Great website</title>
  <meta name="description" content="In this post we&#39;ll">
  <meta name="keywords" content="software engineering">
  <meta name="author" content="Jordan Hudgens">
</head>
```

If you're building out a website, you need to add these meta-data information, as that's the only way your website is going to be found.  If you're interested, you can go to different websites and see their source by right-clicking on the page. This should give you an idea of the different tags that can come under the `<head>` tag.  Just remember, none of this information will be visible to the users or visitors.

##Creating Page Components with the Div Tag

This guide examines one of the tools that you will use constantly when working with HTML projects: the <div> tag. In this material you will learn how to structure a site and organize page components using the div tag syntax.

In this section, let's look into the `<body>` tag. All the content shown on the web page goes inside this tag.  Let's start typing some content, like this:

```html
<body>
 <h1>Hi there again</h1>

 My content goes here
</body>
```
We'll start with the heading tag, but we won't talk much about it in this section.

When you start typing your content, it gets displayed on your browser and it may seem fine. What happens when you want to style some parts of your content in a certain way?

For that, you need to put it inside a container that'll allow you to apply a specific style to it. If you look at the above content, how can you make it bold or change color to it or just do any other change you want?

This is why it's a good idea to separate the content inside your `<body>` tag into different compartments, so you can add a specific style to each. In addition, it also gives a better organizational structure to it.  

Though there are many ways to do it, one of the most popular option is to use `<div>` tags for this compartmentalization, and this is what we're going to do throughout this course. In fact, nobody puts anything directly into the body tag as it is hard to follow. Instead, `<div>` tags are used extensively to separate the content.

`<div>` stands for divider, and it has an opening and closing tag, like this:  `<div> content </div>`

We can now move our content to the `<div>` tag. It is usual practice to put the opening and closing tags on different lines, and the content in between, like this:

```html
<body>
  <h1>Hi there again</h1>

  <div>
    My content goes here
  </div>
</body>
```

This practice is followed because most times, `<div>` tends to have nested elements, classes and stylesheets associated with it, so this pattern makes for easy readability.  Also, there is no limit on the number of `<div>` tags you can have, so more is always better.

Next, we're going to talk about nested `<div>` tags. In general, it's hard to see just a single `<div>` tag because you'll have lots of different things inside the same set of tags. Also, you might want to place each element in a different part of the page. This is why it's common practice to have `<div>` tags nested inside of other `<div>` tags.

For example, let's have two lines of content inside the same div.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/div-same-line.png)

Though we have the two sentences on two different lines, they are displayed on the same line on the browser. This is because HTML doesn't recognize end of line and newline characters. Now, if you want them on two different lines, you'll have to use nested `<div>` tags, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/nested-div.png)

Cool, right?
In short, `<div>` tags are one of the most important tags, and you'll be using a lot of them while coding. It's a great way to organize your structure and compartmentalize different elements.  Also,  it's the best choice when you want to have content on different lines. Lastly, it's perfectly fine and quite common to have `<div>` tags nested inside other `<div>` tags.

##Implementing Inline Components with the Span Tag

This guide explains how to use the <span> tag to customize the look and feel of inline content and organize code components inside of divs.

In this video, we are going to learn about a close cousin of `<div>` called the `<span>`.  In the last video, we learned about `<div>`, and its many benefits. A `<span>` is similar to `<div>`, but comes with some differences.

Let's start with an example.

```HTML
<span>My amazing content</span>
```

If you look at the display, there are some differences that are evident right away.  The first thing that strikes is the content inside `<span>` tag is indented, as this how HTML renders `<span>` when compared to `<div>`.  A more important difference is that the `<span>` tag does not create a line break like a `<div>`.

Let's move our `<span>` tag inside the first `<div>`, and if you see, the content just gets added to the content of the `<div>`.

```html
<div>
My first type of content
<span>My amazing content</span>
</div>     <!-- My first type of content My amazing content -->
```

If you're wondering why we use a `<span>` tag then, it's simply to select items on a certain line.  Let me show you how exactly that works.

Let's go to the third `<div>`, and say, we want to bring a visitor's attention to the words "type of content", then we can put that content inside a `<span>` tag. This is called an inline tag.

```html
<div>
my third <span>type of content</span> goes here
```

If you see, nothing obviously changed there because we are not doing anything special. To see the difference, we'll quickly look at some CSS, though we'll learn about it in depth later.  I'm going to change the color of this text to red, with the code:

```
<span style="color: red;"> type of content </span>
```

Now, if you see, the text color is changed to red.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/red-text.png)

Don't worry about the style or the syntax now because we'll go through it in detail.  For now, just understand the difference between a `<div>` and a `<span>` tag, and how you can use both.

In short, `<span>` allows you to select some parts of the sentence and change its style, without giving a line break. If we were to use `<div>` here instead of a `<span>`, this is how the content will look.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/div-not-span.png)

This is definitely not what we want. All that we wanted to do was to change the style of a few words within a sentence, and for this, `<span>` is the right tag.

##Integrate Headings into Web Pages

In this guide you will learn how to add headings to a web site, including working with all the heading options that will automatically alter the size and emphasis for content.

This is going to be a fun session, as we're going to learn about heading tags.

The largest default heading in HTML, typically your title, is Heading 1. This is represented as `<h1></h1>`.

 If you want a smaller heading, you can choose Heading 2, that is represented as `<h2></h2>`, and for something smaller than that, it's Heading 3, and so on .

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/h1-h5-tag.png)

 If you see, the default size of each text goes smaller as we go down the Heading list. The Heading 5 tag is smaller than the default text.  In the real world, there's only a small chance that you'll use `<h5></h5>`, but it's still good to know how it looks.  

One more thing about these tags is they all start in a new line, so in this sense, they function almost like a `<div>` tag.

 Let's see an example. We'll create a `<div>` tag and have two lines of content, say, "Line 1" and "Line 2". They are displayed side by side. Now, if we add a `<h1>` tag to the first line, the second line is automatically moved down.  

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/h1-droping+down.png)

So, if you put anything inside a heading tag, it'll be on a line by itself.

##Using Multi Line Content with Paragraph Tags

This guide explains how you can add multi line content into a website by implementing paragraph (<p>) tags into a website.

In this video, we are going to walkthrough how to use paragraph tags.  In general,  it's common practice to have all content inside paragraph tags for a better structure.

Implementing a paragraph tag is fairly simple.  Simply have a `<p>` tag before your content, and end the paragraph with a `</p>`.  So, any content should look like this:

```
<p> My first type of content </p>
```

If you see this on the browser, you'll notice a little bit of padding around your sentence, and this is something that comes by default from HTML when you use paragraph tags.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/padding.png)

This tag also comes handy when you want to have a bunch of sentences like your typical paragraph, as you can see the same structure in your browser too.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/paragraph-padding.png)

Such a readable structure is vital for any corporate website or blog that you want to create.  You can now add as many paragraphs as you want.

Also, it's a good idea to have the opening and closing tag on a new line, just like how we did for the `<div>` tag earlier.  This helps with code readability, and also reduces the possibility of omitting the closing tag.  However, it is optional, as nothing will change on the browser.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/%3Cp%3E-on-new-line.png)

So, this is all about paragraph tags, and they are fairly straightforward. Just remember, it comes with its own padding and new line character.

##Working with HTML Hyperlinks

This guides examines how to add HTML hyperlinks to web pages, including options that include linking to 3rd party website and opening up new tabs when a link is clicked.

In this video, we're going to see how to integrate links with HTML.  

We'll start by creating a new `<div>` tag.

Next, to create a link we need to use a tag called `<a href>`, like this:

```
<a href = "your link"> content that needs to be linked </a>
```

```html
<div>
  My great <a href="http://google.com">article</a>
</div>
```

On the browser, you can see a link to the word "article".

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/url-link.png)

When you click on this underlined word, it'll take you to the link you want, which in this case is "www.google.com".

There are different options associated with the `<a href>` tag, and the most important one is `target`. You can give different variables for this `target`, though the most popular one is `blank`. What this essentially means is that you're asking the browser to open the link in a new tab., so you don't have to leave your current page. This practice is considered a standard one as it provides a better user experience. If you're the owner of a page, you don't want the user to leave your page to view another link, and this is where this `target` option comes handy.

```html
<div>
  My great <a href="http://google.com" target="_blank">article</a>
</div>
```

That said, there are some situations when I don't use it.  Typically, when a user is navigating within the same website, it makes no sense to open a new tab. Let's say, a user is in the home page of a website, and she wants to navigate to the products page. In such a case, it makes no sense to open the products page in a new tab.  In fact, a rule of thumb is, use this option when users are navigating to a different website, and not when they want to explore the same website.

To recap, we use a tag called `<a href>` when we have to include links to a web content.  The most important attribute of this tag is `target`, and you typically use this when you include a link that'll take the user to a different website. However, if they're navigating within the same website, you can skip this option.

##Adding Page Breaks with the Horizontal Rule Tag

This guide shows you how to add a horizontal rule to a web page that separate page components with a horizontal line.

In this guide, we're going to see how to use the horizontal rule tag.  If you're not familiar with this tag, what it does is, it gives a line break as well as a horizontal line that you can see on the browser.

This is particularly useful when you have a ton of paragraphs, and you don't want them to run over each other.  It's commonly used in blogs, especially when a separation is required between the content and information about the author.

To implement it, all that you have to add is the tag `<hr>`, and it doesn't need a closing tag as you're not going to put anything  inside it.

If you refresh the browser, you can see the horizontal line.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/horizontal-line.png)

However, this line that comes by default, doesn't look all that great. This is why tools like Bootstrap and Foundation offer different styles.  They may be thicker, have a different color or could have a subtler feel to it. This way you have some more options for designing your web page.

##Integrating Line Breaks into HTML Pages

This guide walks through how to use the <br> break tag to add line breaks on a website.

In this video, we're going to learn how to add line breaks in HTML.

In our code, we have `<hr>` tags to put a visible horizontal line, a `<p></p>` tag to box a bunch of sentences together and a `<div></div>` tag to compartmentalize different elements. Now, what happens if we want to have a line break within a paragraph?

We can create another `<div></div>` and nest it inside the `<p></p>` tag, but it's not necessary.  An easier way is to use the break tag, like this:

`<br>`

```html
<p>
   Lorem ipsum dolor sit amet, consectetur adipiscing elit, <br>sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</p>
```

In the output, you can see the line break.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Line-brake.png)

It's similar to the `<hr>` tag, but only moves the content to a new line. It doesn't create a new paragraph or do anything else for you.

You can also force a line break inside a heading tag, like this:

```
<h1> H1 <br> Tag <h1>
```

The output will be:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/header%3Cbr%3E.png)

However, it is bad practice to force a line break inside the heading tag. In fact, I've never see a production site that does this.

Personally too, I use `<br>` only rarely because I don't find the need to use it often.

##Creating HTML Numbered Lists

This guide walks you through how to use the HTML Ordered List tag to create numbered lists on a website.

One of the most popular elements in HTML is lists, and we're going to learn about it in this video.

There are two types of lists - ordered and unordered. The main difference between the two is that ordered lists use numbers while unordered lists use bullet points.

We'll start with ordered lists. Let's create a new `<div>` , and inside it, create a tag called `<ol>`. This tag stands for "ordered lists". Now, close both the tags first, and then, between the opening and closing `<ol>` tags, add your items with the tag `<li>` that stands for "list". At the end of each item, have a closing `</li>` tag.

So, it should look like this:

```html
<div>
  <ol>
    <li>My first point</li>
    <li>My second point</li>
    <li>My third point</li>
  </ol>
</div>
```

The output will be an ordered list.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/real-orderd-list.png)

Remember, when you use `<ol>` tag, it'll display a numbered list, regardless of the content you put against each list. For example, if you put the second item as "My third point", the output will be:

2. My third point

You can also have nested tags inside your `<li>` tag. Let's say, you want to link the content of your list to another website, you can say,

```html
<div>
  <ol>
    <li>My first point, with <a href="http//yahoo.com">reference materials</a></li>
    <li>My second point</li>
    <li>My third point</li>
  </ol>
</div>
```

So, anytime you want to have an ordered list of items, use the tag `<ol>`, and list each element within a nested `<li`> tag.

##Working with Bullet Point Lists in HTML

Learn how to use HTML bullet points, including tips on how to give your bullets a unique set of styles.

In the previous video, we saw how to create ordered lists, and now, we're going to learn to create unordered lists, also commonly known as bullet points.

To do this, we are going to use a tag called `<ul>` that stands for unordered list. Inside this tag, we're going to list out elements with `<li>` tag, just like how we did for ordered lists.

```html
<div>
  <ol>
    <li>My first point, with <a href="http//yahoo.com">reference materials</a></li>
    <li>My second point</li>
    <li>My third point</li>
  </ol>
</div>

<div>
  <ul>
    <li>My first point, with <a href="http//yahoo.com">reference materials</a></li>
    <li>My second point</li>
    <li>My third point</li>
  </ul>
</div>
```

If you see, much of the code is similar, and that's a good thing with lists. You just have to remember `<ol>` for number lists and `<ul>` for bullet points, and the rest of the content will go inside `<li>` tag.

The output will also be the same, except one will have numbers and the other bullet points.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/lists.png)

Typically, you see ordered lists only when you want to have something shown in a specific order, like a workflow, where you'll have to complete the first task before moving to the second one, and so on. In all other cases, unordered lists are best, to avoid confusion. Let's say, you want to showcase your skills to a freelance client. If you use an ordered list, it may be quite confusing as the client would think you know the first technology better than the second, which may not be true. This is why it's best to stick to unordered lists when you don't need to show something in a specific order.

Now, `<ul>` gives us some options with respect to the type of bullet point we want to use. The default is disc, but we have three other options, namely, none, square and circle.

To implement these styles, the code should be:

```
<ul style ='list-style-type: disc;'>
 ```

Your style options include,

disc - black circle, which is the default.

none - no bullet point is displayed, but the list remains the same though. This is best when we want to use a list, but without any kind of bullet point. This option can be particularly useful when you have to list content that comes with a little "-" before it, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/dash-list.png)

Adding a bullet point will make it messy, so you can simply use the "none" option.

square - a bullet point that resembles a little square. Personally, I like this option and use it a lot.

circle - a bullet point that looks like an empty circle. Though it is similar to disc, here you can only see the outline of the circle.  I'll put both so you can see the difference.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/circle-list.png)

So, that's all about the `<ul>` tag.

##Working with Bold HTML Styles

This guide explains how to make text bold by using the <b> and <strong> HTML tags, including walking through when you should choose one tag over the other.

In this section, we are going through styling choices, and in this video, we are going to see how to add emphasis or bold styling to content.

There are many ways to do it; CSS is a good choice, but we'll get to it later. For now though, we'll use HTML's bold tag to do this.

As always, let's create a `<div>`, and put a paragraph of text in it. To make the first word bold, just add a `<b>` tag and close it off at the end of the word.

```html
<p>
   <b>Lorem</b> ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure <br>dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</p>
```

The output will have the first word in bold.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/bold-word.png)

Alternately, you can also use a tag called `<strong>` instead of `<b>`. If you refresh the browser, both the tags will produce identical results. However, there is a subtle difference between the two.  The `<b>` tag simply shows the content inside of its tag in bold, whereas `<strong>` is used to emphasize a specific word. This difference is particularly evident when using an older browser or by a person with seeing or interpreting disabilities. This means, 99.9 percent of people are never going to know the difference, but it's always good to know that a difference exists.

Also, the `<strong>` tag is relatively new, so it won't work in browsers that are more than a decade old, like IE 6. So, if you're building for older browsers, always use `<b>` tag.

##Using the Italic Style for Text

This guide walks through how to add italics to text components using multiple HTML5 style tag options.

```html
<p>
   <b>Lorem</b> ipsum <strong>dolor</strong> sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. <i>Duis</i> aute irure <br>dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</p>
```

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/italics.png)

##Comprehensive List of HTML Style Tags

This guide walks through how to use the full list of built in HTML style tags, including tags for showcasing mathematical equations, highlighting text, and many more.

In this guide we are going to review the comprehensive list of **HTML style tags**.

Let's start by creating an unordered list *(bullet point list)* using the tag `<ul>` and we'll put each style on a different line with the `<li>` tag.

```html
<ul>
  <li></li>
</ul>
```

### Mark Style

The first style is going to be the **marked** text tag, you can use this tag to highlight a particular word, phrase or value.  The tag for this style will be `<mark>`.


```html
<ul>
  <li>The <mark>marked</mark> text tag</li>
</ul>
```

### Small Style

The next style is the **small** text tag, `<small>`, this style will make a particular word smaller in size.

```html
<li>The <small>small</small> text tag</li>
```

### Deleted Style

The next one is the **deleted** text tag, represented by the tag `<del>`. This tag will have a line right through the word to show that it is deleted. A great an example of when you could use this is for teachers. You can use this style when you want to show students the right way to spell a word. You can delete the wrongly-spelt word with this tag, and insert the right spelling.

```html
<li>The <del>deleted</del> text tag</li>
```

### Inserted Style

Moving down the list of HTML styles, we have the **inserted** text tag next, and this is represented by the tag `<ins>`. This tag will underline a particular word or phrase, so you know it is inserted.

```html
<li>The <ins>inserted</ins> text tag</li>
```

### Subscript Style

The next one is **subscript**, and the tag for this is `<sub>`. This tag is useful when you want to teach or represent logarithms or any other mathematical concept that uses subscript numbers.

```html
<li>The <sub>subscript</sub> text tag</li>
```

### Superscript Style

As you might imagine, similar to subscript, there is a **superscript** tag, represented by the tag `<sup>`. This tag raises the word or number by a few pixels, and is typically used for representing exponents.

```html
<li>The <sup>superscript</sup> text tag</li>
```

**Both the subscript and superscript tags are quite handy for mathematical expressions. They are also easy to represent when compared to using CSS styling.**

### Pre Style

The next tag gives us the ability to put in a programming code. It's called the code or `pre` tag, and is represented by `<pre>`. This tag converts the word into a code-like font such as Courier. Also, it pushes the text to a new line.

```html
<li>The <pre>pre</pre> text tag</li>
```

I use this tag quite a bit to show demos to my clients.

### Quotation Style

The last style is the **quotation** tag, represented by `<q>`.  As the name suggests, it adds quotes to text, and doesn't require you to add quotes to the code.

```html
<li>The <q>quotation</q> text tag</li>
```

If you're thinking it's easier to use quotes instead of the tag, you're probably right. However the HTML development team thought it was important enough to include in their codebase, so I thought I'd include it in this guide.

* * *

Remember, each of these above styles can be implemented using CSS, and we'll see how to do that later.  For now though, it's good to know the different options you have.

##How to Add Images to Websites

This guide walks through how to add images to websites with the <img> tag, including an examination of the various style options you can apply to the pictures.

This is going to be a fun video,  as we're going to learn how to work with images in html.

As always, let's start off with a new `<div>`. Inside it, we'll use the image tag, `<img>`. It comes with an option called source, where you can specify the path or the URL of an image. So, it is represented as:

```
<img src = 'URL' >  
```

URL is the string you'll find on the browser address.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/URL.png)

I prefer to use wikimedia.org, as the images are free for reuse.

Copy this URL and paste it in your image tag.

```html
<div>
  <img src="https://upload.wikimedia.org/wikipedia/commons/6/60/Mount_Kilimanjaro_Dec_2009_edit1.jpg">
</div>
```

You can now see the same image on your HTML page.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/image+on+your+url.png)

If you see, this image is probably too big, and you'll have to scroll horizontally to see the entire image. To avoid this, you can reduce the width of the image, with the `width` option.

```html
<div>
  <img src="https://upload.wikimedia.org/wikipedia/commons/6/60/Mount_Kilimanjaro_Dec_2009_edit1.jpg" width="300">
</div>
```

Now, the image is a lot smaller.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/smaller-url-image.png)

You can play around the width a bit, but remember the value you're passing is the number of pixels.  You can also use percent, when you're unsure of the right size in terms of pixels.  For example, if I put the width as 100%, this means, the image will fit into the browser window perfectly. If you shrink the size of your browser, say for smartphones, the image will be correspondingly resized.  

Like `width`, you also have the `height` option that you can use to resize your image. The problem with using both these options together is that the aspect ratio may not be maintained. If you choose to have a width of 800, and a height of 100, the image will look stretched horizontally. Likewise, if your height is bigger than your width, then the image will be stretched vertically. Since the aspect ratio is not maintained, this is probably not the best way to resize images. A better way is through CSS, and we'll see how to do it in later videos.

The next option we're going to talk about in this video is the `alt` option. It helps with SEO, so it's always important to use this tag. In addition, it helps with accessibility. If someone with disability is using your website, the words you put in the `alt` option will be read out to them.

```html
<div>
  <img src="https://upload.wikimedia.org/wikipedia/commons/6/60/Mount_Kilimanjaro_Dec_2009_edit1.jpg" width="800" alt="Kilimanjaro">
</div>
```

##Mapping Links on Images

This guide walks through how to mapping feature in HTML to place multiple links on an image based on coordinate values.

In this video, we're going to continue working with image tags.

In the last video, we saw how to use a URL as the image source. You may not always want to use a URL, and instead, have one from your local computer or server.

To do that, let's create a `<div>` and an image tag. Here, we'll use a relative path,  as opposed to the absolute path that we have used earlier.  An absolute path is typically a website that you hard code while a relative path is a path that depends on the location of the HTML file and the image. For example, if you have both the image and HTML file on your desktop, you can simply have the name of the image file as the source.

```html
<div>
  <img scr="duck.jpg">
</div>
```

You can add width, height and alt options, as with the previous video.  Now, let's say, you have all your image files inside a subfolder on your desktop. To access these images, you'll have to change the path to include the subfolder.

```html
<div>
  <img scr="duck/duck.jpg" width="145" height="125" alt="Cool Duck">
</div>
```

Next, we'll see how to make images clickable. One way is to wrap it inside a `<a href>` tag, like this:

```html
<div>
  <a href="http://devcamp.com">
  <img scr="duck/duck.jpg" width="145" height="125" alt="Cool Duck">
</div>
```

There is also another way to do it, and this is to use an option called `usemap`. To use this option, we are going to create an ID called "ducklinks" or just about anything else you want. We are going to go over in depth about IDs, and I have a whole section dedicated to it. For now, just remember that IDs start with a "#" sign.

```html
<div>
  <a href="http://devcamp.com">
  <img scr="duck/duck.jpg" width="145" height="125" alt='Cool Duck' usemap="#ducklinks">
</div>
```

Now, we have to give a value for "#ducklinks", and for that, we use a `<map>` tag.  A cool thing about this tag is that it allows us to segment the image into different parts, where each part can take the user to a different link. For example, we can make the right side of the image go to one link and the left side to another.

In the `<map>` tag, the first thing we'll do is give a name, and this name should match the value in the `usemap` option, but it should be without the "#" sign. This name is what connects the `usemap` with the `<map>` tag.

Next, we have an `<area>` tag inside the `<map>` tag that allows us to decide on the area that needs to be clickable. Here, `<area>` takes two options, namely, `shape` and `coords`. You can choose from `rect` or `circle` for `shape`, and for the `coords`, you'll have to mention the values.  You can also have an `alt` option if you like.  Lastly, put a `<a href>` tag, where you'll mention the URL that'll be opened when a user clicks that part of the image.

```html
<map name="ducklinks">
  <area shape="rect" coords="0,0,25,25" alt="goes to google" href="http://google.com"></area>
</map>
```

If you refresh the browser, you can see that the image is clickable only in the area that falls within the mentioned coordinates.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/map-link.png)

Now, let's change the coordinates a little bit, to check if another part of the image goes to a different site.  Then, let's change the shape to circle. For the rectangle, you gave four coordinates, but for circle, you need to give only three.

```html
<map name="ducklinks">
  <area shape="rect" coords="0,0,25,25" alt="goes to google" href="http://google.com"></area>
  <area shape="rect" coords="40,40,25,10" alt="goes to yahoo" href="http://yahoo.com"></area>
  <area shape="circle" coords="125,75,50" alt="goes to devCamp" href="http://devcamp.com"></area>
</map>
```

And this is the clickable part of the image.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/circle-link.png)

You can see the circular area it covers.

I think this is really cool, as you can get to three different sites, simply by clicking on three different areas within an image. This can be particularly useful when you can't use JavaScript for a website, and yet you want users to click on images. I had to work on a similar project in the past, where the client's platform would not allow me to use JavaScript. Still, I had to make every item from a product catalog image go to that particular product's URL page. I did this using the `<map>` tag, so it might come handy for you too when you start doing projects like this.

##How to work with Custom Tags in HTML

This guide walks through how to use custom HTML tags that will allow for explicitly declaring how your code is organized.

So far, we've seen some of the standard HTML tags, and in this video, we're going to see how to work with custom tags.

We can create our own HTML tags and use them for web pages. In general, you may not have time to create and use these tags, but if you're into things like angular JS, it can come handy.

Let's say, you want to create a navigation element using your own tag. Let's also say you've named it `<nav>`. You can put it inside a `<div>`, and even have elements nested inside it.

```html
<div>
  <nav>
    <h3>My Navigation Element</h3>
  </nav>
</div>
```

Since we're not using a standard tag, you change `<nav>` to `<widget>` or just about to anything else you want, and nothing will change.

One thing you need to keep in mind here. If you're working for a new client who doesn't know you or trust you yet, there is always a chance for them to put your code through a HTML validator. If that happens, custom tags will break a lot of validation because these validators only pass standard tags.

However, this doesn't mean you shouldn't use these tags at all, as many clients, won't bother much about the code as long as the functionality is good. In such cases, these custom tags can give you a nice structure, and can make your code more readable.

##Adding Comments to HTML Code

In this guide you will learn how to use HTML comments to add documentation to your code base.

In this video, we're going to work on something that you can't see on the browser -  comments. But this doesn't mean it's not important.

When you use comments, you're making notes or giving instructions to yourself, or you can also let other developers know something about your code.  As you've guessed, these comments can be seen only on the source file, as they'll not be rendered on the browser.

To write a comment, use this syntax:

```
<!-- This is my great comment -->
```

Obviously, nothing is displayed on the browser.

However, if you right-click on the page and choose "View source code" option, you can see the comment in that file.  Remember, anyone can see this comment through the browser, so don't put anything that you don't want others to see, like your passwords.  Sometimes, I've seen comments where the developer insults his boss and things like that. It's best to refrain from such things.

Also, you don't need comments for things that are self-explanatory. For example, why should put a comment saying "bullet points" before a `<ul>` tag, as the tag itself means bullet points. Such comments are simply a waste of time and effort.  Also, some developers think they need to explain any complex task they do. Though it explains all that they do, it is not considered good practice because you may change the code, but can miss to change the comment. As a result, the comment may not reflect the changes you make and will no longer be relevant to the reader.

I've seen these mistakes made by other developers, and this is why I recommend not repeating them.

This doesn't mean comments are bad. In fact, they are a good way to bring attention to a specific code, so you or others know about it. It's best used before custom tags, so everyone knows why these tags are there in the code.

```html
<div>
  <!-- Start of nav -->
  <widget>
    <h3>My Navigation Element</h3>
  </widget>
  <!-- End of nav -->
</div>
```

In short, use comments sparingly and only in places where it makes sense.

##Guide to Using Web Developer Tools

Learn how to analyze code in the browser by leveraging the web developer tools provided by Chrome.

In this video, we're going to walkthrough a very cool feature.

As you know, HTML and CSS give shape to websites. If you want to see the code of any web page, you can right-click on the page and choose the "View page source" button  This code is obviously different from page to page, even within the same website.

This option is not helpful when you want to debug a page. Let's say you create a page, fill it with content and upload it. Only later you realize there's an error and you need to fix it. You can't do that through "View page source", and this is where the developer tools come in.  A better way would be to right-click the browser and click on an option called "inspect".  This brings up a panel for you, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/view-page-source.png)

This is a powerful tool, and I'll show you why. You can follow along, go to devcamp.com or any other site you like.

The leftmost button allows you to select any element on the page.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/select-element.png)

If you look at the right-hand side, you'll see all the style elements. Though we haven't covered CSS yet, it'll be good to see what it has. When you know CSS, this panel can be really helpful for debugging.  You can even make changes, and see them real time on the page.  You can add new styles too, if you want.

However, one thing to note here is the change you make is visible only for you and only in this session. Let's say you change the text color of a button to blue, you're the only one who can see it. If another person is accessing the same site, they'll still see only the default black text.  Also, if you refresh the page, the change you made is lost, and you'll also see only black text.

Now, if you select a particular element, you can see the `<div>` ID associated with it, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/%3Cdiv%3EID.png)

You can change the color or do anything to see how it looks on the browser.  CSS, in general, will encompass a set of similar elements. In the above example, any change you make to the text color will apply to all the four paragraphs. However, if you want to change only one paragraph, you can what is called a CSS selector to just select the style for that one paragraph. This is just a quick preview, and we'll get into all that later.

If you like what you see, you can take this change to your CSS file, so the change is permanent.  In this sense, this is more like a staging area where you get to play around with the code to see what looks better.

Continue exploring on the site and see through different elements.  Another cool thing is, if you right-click on any image on the web page, you won't have the option to save or download it. If you still want access to the source image, look for the source URL on the CSS panel and click on it. This will take you to the original image.

I'd suggest you explore the site, make some changes to the CSS style to get a feel of it. If you see, there are quite a few tabs on the right side. The "Styles" tab is probably where you'll spend a lot of time. The "Computed" tab gives you a graphic representation of the layout. "Event listeners" and "Properties" are advanced stuff, and I rarely find the need to use them. "DOM Breakpoint" are where you'll set breakpoints to check for certain behavior.

CSS can be confusing to start with. It's best to read it from top to bottom, as you may have two conflicting styles that can cause for one of the things you're working to not show up properly.

So, that is an introduction to know how to use web developer tools inside a browser.

##Working with HTML IDs

This guide examines how to set and work with an HTML ID, this is a key concept to learn because IDs will be one of the ways that you can select page elements to apply styles.

In this video, we're going to talk about how we can give differentiation to different elements on a page using IDs.

Let's take a practical example.  Go to wikipedia.com, open the inspect tool, and hover over any element. You can see that each element has an ID associated with it. Each ID is unique on the page, so you can grab that ID and work with it.

If you want to add an ID to any element on your site, go to that element, add the word "id" and gave a unique name to it. This name should be inside double quotes, and it should not contain a space. Underscores and dashes are a better way to give a meaningful name to each element.

```html
<body>
  <div id="paragraph_one">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>
</body>
```

You can add ID to any element, even heading tags.

If you open that page on a browser, you can see the ID associated with it.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/h1-ID.png)

These IDs give us a granular level of control, so we can make changes to specific elements.

So, this is how we can add IDs to HTML elements.

##Working with HTML Classes

This guides explains how to work with HTML classes, which are selector attributes that can be used multiple times on the same page.

In the last video, we talked about HTML IDs, and in this one, we're going to talk about classes.

At first look, IDs and classes may seem similar, but they have one important distinction -  IDs have to be unique whereas classes can be reused. In other words, multiple elements in your page can have the same class, but they can't have the same ID. Though HTML does not throw an error while rendering a page with multiple IDs, it can get quite messy if we're going to use these IDs.  This is why we have to keep the unique.

Classes are mostly used for styling different elements. Let's say, for example, we have a certain style for all titles, and these titles are defined under a class called "Title". Now, if we want to change the font for all the titles, all that we have to do is simply change it in the class, and the change will be reflected everywhere. This is a lot easier than changing the style of every title on your page.

Now, let's change all IDs to classes, refresh the browser, right-click on the page and select "Inspect". If you see, the "#" tag is not there anymore, and this replaced with a "."

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/h1%23title.png)

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/h1.title.png)

This is because "#" symbol is used only for IDs, whereas classes are represented by "."

If you want to see the distinction more clearly, change one of the values to ID, and keep the other one as class. Now, if you refresh the browser, the difference is evident.

I hope this gives you an idea of IDs and classes. You'll appreciate these differences better when we start using them in the next section.
