#Chapter 4 Guide to HTML Forms



##Introduction to HTML forms

This guide walks through HTML form basics, including a discussion on how forms work and what code needs to be implemented for a basic form structure.

In this section of the course, we're going to walk through how to use HTML forms.

HTML forms are an important part of application building. At the same time, you can't use it as a mere HTML code. Rather, you'll have to tie it with a server code such as Rails, PHP, NodeJS, or anything similar. This is because by its very nature HTML is stateless, which means it's not going to know what information is sent from page to page, and where it is stored. So, no kind of functionality such as sending emails is possible with HTML forms, until you integrate it with a server code.

That said, we're going to see how to create a basic form skeleton.

There are a few requirements while creating a form, and this is what we'll go through in this video.

Let's start with a `<form>` tag.  There are some attributes that have to go inside of this form tag, and they are:

action - The page that we want our system to get directed to.

method - You can use GET or POST as methods, and they are the only ones you can use. When you use GET, all the parameters will get passed into the string itself.

For example, if you open Google and search for any string, then this value gets added to the string, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Introduction+to+HTML+forms+%23+520/image1.png)

If you look at the URL closely, the first parameter is something called "safe" that Google has, in order to check if the safe search feature is on or not. The second parameter is "q", which is the short form for query, and this is what I typed in the search box.  Since our URL can't have spaces, it is represented by the symbol "+".

In the case of POST, none of this information is available in the URL.  POST is mostly used for secure HTML forms, where you don't want anyone to know the information that is being passed.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Introduction+to+HTML+forms+%23+520/image2.png)

In this case, I'm submitting an email ID and password, so it's not a good idea to pass such sensitive information in the URL. For such secure forms, we use the POST method.
So, those are the two things required in an HTML form.

Inside this form,  we're going to create a "Submit" button, just for a demo. This way, you can see the form on the browser.  You can change the content on the button using a parameter called `value`.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>HTML Forms</title>
  </head>

  <body>
    <form action="contact_form.php" method="get">
      <input type="submit">
    </form>
  </body>

</html>
```

So, this is the form skeleton.  



##Working with HTML Text Input Fields

In this guide you will learn how to integrate HTML text input fields, including a discussion for how to nest input fields inside of an HTML form structure.

Now that we have our form skeleton in place, let's see how to add some text input fields.

In this section, we won't focus too much on styles or CSS, rather we'll look at the core functionality. Let's  start with taking input for the variable "name".  Remember, how we had input type as "Submit" for our submit button? Here, we'll have text as the input type to denote a text field.

```html
Name: <input type="text" name="name">
```

The `name` for this text field is "name". Don't get confused here, the `name` in blue is the attribute while the "name" in quotes is the value for that attribute.

We're going to have another attribute called `email`, and have the `name` attribute set to a value "email."

After this, your output should look like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Working+with+HTML+Text+Input+Fields+%23+521/image1.png)

Though this looks neat, I don't prefer to type in the words "name" and "email". Instead, let's use HTML labels. All that we have to do is have a `<label>` tag, and have the text placed between the opening and closing tags, like this:

```html
<body>
  <form action="contact_form.php" method="get">
    <label form="name">Name:</label>
    <input type="text" name="name"><br>

    Email: <input type="text" name="email"><br>
```

Nothing would appear to have changed in the browser. However, if you hover over the label, it'll turn into a cursor, and when you click on it, most browsers will activate the input field. If you hover over the text "email", nothing will change though. That's the key difference between using labels and normal text.  This difference can be particularly important for mobile devices.

Now, let's make the same change for email too.

Moving on, let's say you want users to know what kind of information to type in each field. You can put placeholders in each field, with this code:

```html
<label form="name">Name:</label>
<input type="text" name="name" placeholder="Jon Snow, etc"><br>

<label form="name">Email:</label>
<input type="text" name="email"><br>
```

If you see, the name "Jon Snow, etc" will be the default value in the name field, and this will go away when you start typing the value you want.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Working+with+HTML+Text+Input+Fields+%23+521/image2.png)

This can be particularly helpful when you want users to enter a value in a specific format. For example, if you want users to enter their last name first followed by their first name, this placeholder can act as a guide.

This placeholder is different from another attribute called `value`. While placeholder is to suggest the right format, value is the default value that'll be present in a text field.  This is the code for both,

```html
<label form="name">Name:</label>
<input type="text" name="name" placeholder="SNOW,JON"><br>

<label form="name">Email:</label>
<input type="text" name="email" value="jon@snow.com"><br>
```

And this is the difference in the browser.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Working+with+HTML+Text+Input+Fields+%23+521/image3.png)

One more parameter that we'll talk about in this video is `required`. It does not take any parameters, and as the name suggests, it makes a particular field mandatory for the user.

In other words, if the user doesn't enter a value in this field, then he or she cannot submit the form.

Let's add this attribute to our `name` and `email` fields.

```html
<body>
  <form action="contact_form.php" method="get">
    <label form="name">Name:</label>
    <input type="text" name="name" placeholder="SNOW,JON" required><br>

    <label form="name">Email:</label>
    <input type="text" name="email" value="jon@snow.com" required><br>
```

The output will be:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Working+with+HTML+Text+Input+Fields+%23+521/image4.png)

 Though the above parameter is convenient, it's not enough to truly validate your form.   You also need code on your server side to protect against validations.

Let's say we didn't do any validation on our server side. You can right-click on your browser page and select "Inspect". In the code that pops up, you can always remove the required field, and submit it directly.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Working+with+HTML+Text+Input+Fields+%23+521/image5.png)

This way, you can change your browser code to the way you want. This is also why it's important to have server-side validations too.



##Guide to Text Area HTML Field

This guide gives a step by step set of instructions for how to add HTML text area fields to a form, including an explanation on how to customize the size of text area fields.

In this video, we're going to see how to create large text areas to take input from the user.

To implement this, we'll have to use a separate HTML tag called `<textarea>`. This element is similar to a textbox but is much larger in size, and you can customize its length and width to match your design requirements.

Going back to our example, we'll use a text area to create a field for a message. Let's add a label and a text area.

Now, this `<textarea>` tag can take a number of attributes, so we'll use `name`, and something called `rows`. This `rows` attribute helps you to define the height of your text area. Let's say, you want to fit in 15 rows of content, then you set the value of `rows` to 15, and this is how your text area will look.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Guide+to+Text+Area+HTML+Field+%23+522/image1.png)

As with `rows`, there is something called `cols` that helps you to define the width of your text area.  Imagine an excel spreadsheet, and you'll be able to relate to `rows` and `cols`. One thing to note here is `cols` work slightly different than `rows`. Let's say, you put a value of 15 for your `cols` attribute, this will effectively shrink the size of the text area, so a value of 100 would be better. In general,  `cols` value depends on the character length. if you want your text area to hold 100 characters, then that's what you should specify.

The code is:

```html
<label for="message">Message:</label><br>
<textarea name="message" rows="15" cols="100"></textarea><br>
```

So, this is a great way to create a text area, and customize it to meet your size requirements.
One more cool thing about text area is, you can go beyond the specified `rows` value too. In our case, you can type content for more than 15 rows too.  When you have more content, text area automatically creates a scroll bar, to make it easy for you to read through your content.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Guide+to+Text+Area+HTML+Field+%23+522/image2.png)

In this sense, `rows` value is the content you can see without scrolling up or down.

This is also something you should keep in mind while designing your page. Also, another cool thing is modern browsers allow you to resize the text area in the browser. Simply drag and drop the text area to get the size you want, depending on the amount of text you want to type.

However, the look and feel may change from browser to browser.



##How to Use HTML Form Checkboxes

In this guide you will learn how to use HTML checkboxes into web forms to allow users to select multiple items on a form.

In this guide, we are going to learn how to use checkboxes in HTML.

So far, we've been working on a contact form, so we'll just add a little bit of space and create some example checkboxes.

Let's start with a label, and then create a checkbox with the code `<input type="checkbox">`. As with other elements, we'll have a `name` and a `value`. The `name` attribute should have a value that is the same as the value we give in our label. Another thing to note is the `name` attribute's value should be the same for all checkboxes that are grouped together.

Let's create a few checkboxes like this:

```html
<label for="options">Packing Requirements (select all that apply):</label><br>
<input type="checkbox" name="options" value="premium"> Premium<br>
<input type="checkbox" name="options" value="automated"> Automated<br>
<input type="checkbox" name="options" value="rush"> Rush<br>
```

The output looks like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/How+to+Use+HTML+Form+Checkboxes+%23+523/image1.png)

Obviously, you can select more than one option, as checkboxes are meant for that only.

So, this is how you can create checkboxes in HTML.



##Working with HTML Form Radio Buttons

This guide gives a step by step set of instructions for how to integrate radio buttons into an HTML form. This will allow users to select boolean value types.

Now that you know how to use checkboxes, we'll look at a related element - radio buttons.  The main difference between checkboxes and radio buttons is that you can select as many options as you want in the former, but only one out of the available options in the latter.

We'll start with a label called "delivery".  Next, we'll create a radio button with the code `<input type ="radio">` The `name` attribute should have the same value as that of the label. Also, the `name` attribute should have the same value for all radio buttons, as this is what allows you to select only one. If you have different names for different radio buttons, then you can obviously select all the radio buttons, and this beats the very purpose of it.

 Let's create a bunch of radio buttons, like this:

```html
<label for="delivery">Shipping Preference:</label><br>
<input type="radio" name="delivery" value="in_store"> In Store<br>
<input type="radio" name="delivery" value="shipping"> Shipping<br>
```

The output will be:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Working+with+HTML+Form+Radio+Buttons+%23+524/image1.png)

So, this is how you can create radio buttons in HTML.



##How to Use Select Boxes in an HTML Form

This guide explains how to integrate a select drop down box into an HTML form, including a number of the options available to select box elements.

In this video, we're going to see how to create and use a select box, also known as a dropdown box.  This element gives you a good amount of control, as you can pre-determine the items or choices that are available for a user.

Now, let's add some select boxes right below our text area. As always, we'll start with a label, and call it "source".  Next, we'll create a select box with the tag `<select>`. Inside this tag, we'll use the `<option>` tag for each choice., like this:

```html
<label for="source">How did you hear about us?</label>
<select name="source">
  <option value="google">Google</option>
   <option value="yahoo">Yahoo</option>
   <option value="fb">Facebook</option>
   <option value="twitter">Twitter</option>
</select>
```

One thing to note here is that the name you give in the `value` attribute is the one that gets passed from page to page. So, make sure to give it a meaningful name. The description or the content you provide between tags is only for the user and will have no bearing whatsoever on server-side code.

The output will be a dropdown box.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/How+to+Use+Select+Boxes+in+an+HTML+Form+%23+525/image1.png)

The default value for this dropdown box is the one at the top, which in this case, is "Google." If you have something else, say "Facebook" as the first option, then that'll be the default.
So, that's how you create a dropdown box in HTML.

Now, what happens when you want users to select multiple items from a list?

To do that, simply add an attribute called `multiple` in your `select` tag, and set its value to "true"

```html
<select name ="source" multiple = "true">
 ```

With this code, users can hold the command key and select multiple values like this:

If you're thinking this is rare, you're mistaken, because there are many situations where you'll use it. For example, I built a site called "www.crudelist.com", and here I allow users to select multiple items for the category.

In many ways, this is nothing but a styled version of our dropdown box.

So, that's your introduction to select boxes.



##How to Group Drop Down Form Elements into Categories

In this lesson you'll learn how to group drop down elements into organized categories for select boxes.

In this video, we're going to see how to group elements together in a dropdown box.

Let's create a label and call it `shipping_method`. In general, never use spaces while naming your elements. Instead, use a snake case (which separates two words with an underscore) or camel case (where the second word starts with a capital letter with no space in between).

Next, let's create a dropdown box with the `<select>` tag.  This tag will have no other attributes except `name`.  Next, let's create groups with a tag called `<optgroup>`. This tag takes an attribute called `label` that should have a meaningful name. Inside this `<optgroup>` tag, we can create individual items with the `<option>` tag.

```html
<label for="shipping_method">Shipping Method:</label>
<select name="shipping_method">
  <optgroup label="Business">
    <option value="biz_overnight">Overnight</option>
    <option value="biz_groung">Ground</option>
  </optgroup>
</select>
```

If you look at the output, you'll see that there is a label called "business", and options for it.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/How+to+Group+Drop+Down+Form+Elements+into+Categories+%23+526/image1.png)

You can create multiple groups like this:

```html
<label for="shipping_method">Shipping Method:</label>
<select name="shipping_method">
  <optgroup label="Business">
    <option value="biz_overnight">Overnight</option>
    <option value="biz_groung">Ground</option>
  </optgroup>
  <optgroup label="Residential">
    <option value="res_overnight">Overnight</option>
    <option value="res_groung">Ground</option>
  </optgroup>
</select>
```

And the output will have two different groups.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/How+to+Group+Drop+Down+Form+Elements+into+Categories+%23+526/image2.png)

Ensure that each of these values has a unique name, as that's important from a script standpoint. For example, if you have a value "ground" for both business and residential, then the script will not know which option you've selected. This is why having a unique name is important.

So, this is how you can organize your options in a dropdown box.



##Working with HTML Form Calculated Fields

This guide examines the HTML 5 calculated field element that will perform math on form element values, this includes a basic project example.

In this video, we're going to talk about an interesting element called Calculated Fields that is available only in HTML5.  This element is best used when you want to present some live update on the screen.

For this example, we're going to take a total value, add the cost of shipping to it, and present the final invoice value to the user.

To start with, go all the way to the top. In your `<form>` tag, add an attribute called `input` and pass a value to it. This tag will essentially keep watching if the user types in an input, and will act accordingly. In this case, we want this attribute to calculate the total cost of the invoice and the shipping cost, and we can do that with the code:

```html
<body>
    <form action="contact_form.php" method="get" oninput="invoice.value=parseInt(total.value)+parseInt(shipping.value)">
```

If you find this code weird, don't worry! The idea is just to show you what this tag can do.

Now that's done, let's create the calculated field. As always, we'll start with a label and call it "Subtotal".  Next, we'll create an input field of type text, and have an initial value of 0. Likewise, we'll create another label and input field with the name "shipping." The default value for this text field is 9. Then, we'll calculate the total cost, and for this, we'll use a tag called `<output>`. We'll give a name for the `<output>` tag.

So, the complete code is:

```html
<label for="total">Subtotal:</label><br>
<input type="text" name="total" value="0" /><br>

<label for="shipping">Shipping:</label><br>
<input type="text" name="shipping" value="9" /><br>

Total for invoice: <output name="invoice" for="total tax"></output>
```

You can test it out on your browser. Enter any number in your shipping field, and you'll see that the final output is that value plus nine.  The value of shipping can be updated as well, and the total field would reflect this change.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/Working+with+HTML+Form+Calculated+Fields+%23+527/image1.png)

Let's go back to the code and see how exactly how it works. If you look at the `input` attribute, it says `invoice.value`, and this `invoice` is what we've given as a name for the `<output>` tag. It's absolutely important that these names match.  Similarly, we are taking the value of `total` field and `shipping` field while calculating, so the names of these fields should match with the formula we have in `input`.  

HTML5 parses the integer value of these fields and adds them up, to give us a final value that is stored in `input` tag. When we use the `output` tag, this value is communicated to the `output` tag, so the final value gets displayed.

One thing to note is this element may not be supported by older browsers, typically anything below IE 9.0.

So, this is how you can calculate values dynamically in HTML.



##How to Use HTML Entities for Custom Character Values

In this lesson you will learn how to use HTML entities in order to safely render special characters on a webpage, along with the reason why entities are important.

In this video, we're going to learn about custom HTML5 entities.  These are special entities that allow you to use custom symbols like copyright symbol, ampersands, and things like that.

Though technically you can use these symbols directly on the custom page, it's not recommended because certain browsers will render these symbols differently. For example, "&" is used for different things such as running queries, in GET&POST requests, and other server-side communications.  This is why we use entities, as they'll translate to safe-to-use symbols while getting rendered by different browsers.  For example, to display an ampersand, we can use the code: `&amp;`, and this will render "&" on the browser.

```html
<body>
  <p>Ampersand: &amp;</p>
</body>
```

And the output will be:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Forms/How+to+Use+HTML+Entities+for+Custom+Character+Values+%23+528/image1.png)

So, that's how you can do an entity name.

Instead of name, you can also do a number, like this:

This will also display the same ampersand symbol.

Both the name and number are the same in terms of browser rendering, so it just depends on what you feel most comfortable remembering.

We'll go through more symbols like copyright and registered trademark.

```html
<body>
  <p>Ampersand: &amp; &#38;</p>
  <p>Copyright: &copy; &#169;</p>
  <p>Registered tademark: &reg; &#174;</p>
</body>
```

The next one is an interesting entity called non-breaking space. To start off, type a few spaces and then a sentence. When it gets rendered on the browser, you'll see no space. This is because whitespaces are by default ignored by HTML. If you specifically want to insert a whitespace, you should use this code:

`&nbsp;` or `&#160;`

Remember, never use `&nbsp;`  to give padding to your content as it'll look ugly, and can even throw off the design.

Thus, these are probably the four most popular entities that you'll use. But there are also a few more, and we'll run through them. They are greater than symbol, less than symbol, double quotes, and single quotes.

```html
  <p>Greater than: &gt; &#62;</p>
  <p>Lesser than: &lt; &#60;</p>

  <p>Double quotes: &quot; &#34;</p>
  <p>Single quotes: &apos; &#39;</p>
</body>
```

So, these are some of your common entities.
