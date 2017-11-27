#Chapter 7 Project: Create an HTML Email Template

##HTML Email Project Overview and Instructions

This guide gives an overview of the project to build along with instructions on how to accomplish the features.

In this section, we're going to build a HTML email. So far, we've cloned Google and Pinterest pages, and now we're going to see how to create HTML-friendly emails.
There will be many situations when you want to create a custom email that showcases your client's products or makes certain announcements to their end customers.  The rules for creating HTML emails are slightly different though. Here, you can't create external stylesheets, rather you have to encapsulate all your styles within the email itself.

That said, I want you to try this project by yourself before looking at the solution.  Focus on creating an email that uses a HTML image as the background,  and has text and links.

It doesn't have to be identical to this

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/HTML+Email+Project/HTML+Email+Project+Overview+and+Instructions/image1.png)

but ensure that it contains different elements to make it interesting for you.

##Project Solution: HTML Email Tag Structure

This solution guide walks through how to structure the HTML tags in order to integrate content and select tags prior to adding CSS styles.

For this project, I'm going with a little bit different structure because emails are different from websites.

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
  <title>Marketing Email</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
 </head>
    <body>
    </body>
</html>
```

This is how the basic structure looks like for emails. If you already did some research while trying out the solution yourself, then you'll be familiar with a lot of this boiler plate code.

If you look at the code, we're starting off with `<!DOCTYPE>`, but after that we're typing out some extra meta data information because email engines are much different from web browsers. You don't really have to worry too much about this code, but it's good to know what you should include.

In the second line, we have something called `xmlns`, and this is to helps emails to be compliant with apps such as Outlook and other email clients, so that they read the information correctly.

In the meta data tag inside `<head>`, I'm setting the content type, and effectively telling the email engine to expect UTF-8 charset. In the next meta data, I'm setting the device width and doing other things that deliver the exact design to the end users.

So, you can use this as a skeleton for your HTML emails in the future. It'll be available in the Show Notes section. You can go to "https://github.com/jordanhudgens/html-email". Here, you'll find a file called `index.html` that contains our code, and an image that we'll use as the background.

Next, we'll create content in the `<body>` tag. As always, we'll start with a `<div>` tag and give it an ID. We'll have a nested `<div>` inside which we'll put the text we want. You can put whatever you want here. I'm going to add a subheading, text and links.

```html    
<body>
  <div id="heading">
    <div id="content">
      <h1>Hi, here's my message</h1>
      <h3>And a subheading</h3>

      <div class="alert">
        <a href="#">Checkout weekly specials</a>
      </div>
    </div>
  </div>
</body>
```

Once that's done, we'll create a footer, and we'll have some content here. Specifically, I want to add a custom entity.

```html
<div id="footer">
  <div class="footer-text">
    &reg; ABC Company 2016<br>
  </div>
</div>
```

If you go to the browser, you'll see that we have all the content, even if they look a little ugly.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/HTML+Email+Project/Project+Solution+-+HTML+Email+Tag+Structure/imageA.png)

If you right-click and view the source code, you can see all our code.

##Project Solution: HTML Email Integration of CSS Styles

In this solution guide you'll learn how to integrate CSS styles to customize the styles for the email template.

Now that our content is in place, let's get into styling it.  For this project, we can't use an external stylesheet as the email engine is different from a web browser. This is why we have to go in for embedded stylesheets.

Let's get started with the `<style>` tag in our `<head>`.

First off, let's center the entire body by setting a value of "auto" to `margin`. Next, we'll set a specific width, say 700 pixels, and a `font-family` of "sans-serif". Though we can use custom fonts, I prefer to go with built-in ones for emails.

```
<style>
    body {
      margin: auto;
      width: 700px;
      font-family: sans-serif;
    }
```

Next, we'll work on the `#heading`. Let's set a height of 400px a background color, and a background image of Tesla cars that we decided earlier.  Since we don't want a tiled background, we're setting a value of `no-repeat`. Lastly, we want the background size to be equal to 100%.

```css
#heading {
      height: 400px;
      background-color: #00004d;
      background: url('teslas.jpg') no-repeat;
      background-size: 100%;
    }
```

If you go to the browser, you'll see that its coming along nicely.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/HTML+Email+Project/Project+Solution+-+HTML+Email+Integration+of+CSS+Styles/image1.png)

Next, we'll work on the `#content` where we'll have a padding of 15px on the top and left. Then, we'll set the color of our h1 tag to white and h3 tag to a shade of green, so they're visible on the background.

```css
#content {
      padding-top: 15px;
      padding-left: 15px;
    }

    #content h1 {
      color: white;
    }

    #content h3 {
      color: #6BAE3D;
    }
```

Next, we'll work on the image. We'll have a width of 100% and put a value of 0px for the left padding.

```css
#content img {
      width: 100%;
      padding-left: 0px !important;
    }
```

The next thing that we'll work on is the `alert` class.  If you look at the html code, this is the class that has an external link. Let's give it a greenish color, a padding of 15px all around, and a `border-radius` of 5px. We have to obviously set the `border-radius` separately for each browser. Finally, we're going to set our width and a top margin.

```css
.alert {
      background-color: #00446A;
      padding: 15px;
      -webkit-border-radius: 5px;
      -moz-border-radius: 5px;
      border-radius: 5px;
      width: 250px;
      margin-top: 180px;
    }
```

The output looks much closer to how we want, though there's still some work that needs to be done.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/HTML+Email+Project/Project+Solution+-+HTML+Email+Integration+of+CSS+Styles/image2.png)

The next logical step is to style the link. For this, we don't want any text decorations, but we want a white color and a slightly larger font size.

```css
.alert a {
      text-decoration: none;
      color: white;
      font-size: 1.5em;
    }
```

The email is much better now.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/HTML+Email+Project/Project+Solution+-+HTML+Email+Integration+of+CSS+Styles/image3.png)

If you notice, this is a clickable area that can take you to a landing page or website.

The last thing is our footer. We'll set the background color to green, and the height to 90px. For the text, let's go with a color of white, some left and top padding, and a slightly big font size.

```css
#footer {
      background-color: #6BAE3D;
      height: 90px;
    }

    #footer-text {
      color: #FFFFFF;
      font-size: 14px;
      padding-left: 20px;
      padding-top: 35px;
    }
```

That's it!

The email looks like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/prework/HTML+Email+Project/Project+Solution+-+HTML+Email+Integration+of+CSS+Styles/image4.png)

And I think, that's cool!
