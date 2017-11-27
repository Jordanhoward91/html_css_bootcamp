#Chapter 3 Guide to HTML Tables

##Introduction to HTML Tables

This guide walks through: what HTML tables are, how they should be used, and the basic syntax.

In this section, we're going to learn to use tables in HTML.

Before that, I want you to remember one thing. You should use tables only when you're working with tabular data. In all other cases, you should use CSS styles.  Never design your site to fit into an HTML table, as that would be a complete disaster.  

That said, let's get on with our tables.  As you would've guessed, there is a tag called `<table>` that would create a table for us.  In this example, I want to build a table of baseball players.  To do that, we have to use another tag called <`tr>`, that stands for table row. As the name suggests, each tag represents a single row in the table, so we can have a row for Player 1, Player 2 and so on.  Each of these rows are separated by columns. If you've worked with Microsoft Excel, this should be familiar to you.

Next, we're going to use a tag called `<th>` inside every `<tr>` tag, and this represents the heading for every column.  Let's have four headings, one each for name, average, home runs and RBIs.

```html
<table>

  <tr>
    <th>Name</th>
    <th>Average</th>
    <th>HRs</th>
    <th>RBIs</th>
  </tr>

</table>
```

This is the end of the row, and this is why we have a closing `</tr>` tag.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/Introduction+to+HTML+Tables+%23+512/image1.png)

The next one is going to be a new row, and we'll fill it with information.  Since this is not a heading, we'll use a tag called `<td>`. Every element in our table should be inside a `<td>` tag.  When you fill information, keep the image of a grid in mind. For example, the information should be the name of the player, his average, his home runs and RBIs. This mapping is important while creating tables. So, the code is:

```html
<tr>
  <td>Altuve, Jose</td>
  <td>350</td>
  <td>32</td>
  <td>120</td>
</tr>
```

And the output is,

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/Introduction+to+HTML+Tables+%23+512/image2.png)

You can create more rows like this, and fill them with the right information.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/Introduction+to+HTML+Tables+%23+512/image4.png)

Since I want this to be an admin dashboard, I'll also have edit and delete items.

So, this is how you create tables in HTML.



##How to Style HTML Headers

Learn how to customize the look and feel of HTML table header, including how to select the color and background components.

Now that you know how to create a basic HTML table, we're going to see how to customize the style, and we'll start with the headers.

I'm not going to use an external stylesheet for this one, as I want you to see the styling options in the same page. So, let's start with our `<style>` tag, and use the `<th>` selector.

We'll add a background color of black and a text color of white.

```css
th {
  background-color: black;
  color: white;
}
```

Still, it doesn't look so nice because we're using the default values given by HTML. So, let's style the table first. We'll have `sans-serif` as the `font-family`, and will give a width of 100%, so it stretches through the entire page, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/How+to+Style+HTML+Headers+%23+513/image1.png)

Next, we're going to use an attribute called `border-collapse`, that'll make the table tighter and will remove some of the border lines that we saw earlier.

```html
<style>
  table {
    font-family: sans-serif;
    width: 100%;
    border-collapse: collapse;
  }

  th {
    background-color: black;
    color: white;
  }
</style>
```

The output is:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/How+to+Style+HTML+Headers+%23+513/image2.png)

If you see the default border lines are gone, and that's good!

So, that's how you can style table headings. Play around these attributes a little bit more to get familiar with them.



##Styling Table Rows

In this guide you'll learn how to style table rows, including using the nth child selectors to dynamically style alternating rows.

To continue with our table styles, we're going to style the table rows and headers in this video.

Let's create styling attributes for our `<td>` and `<th>` rows. Though we did styling for `<th>` row earlier, we are going to style the elements inside each cell, so they're applicable to the entire table.

Let's start with a padding of 15px. Next, our items are not lined up properly, so we'll fix that with the attribute `text-align` that'll take the value `left`.

This gives us a much better-looking table.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/Styling+Table+Rows+%23+514/image1.png)

Lastly, we'll add a border that is 1px thick, solid and is grey in color.  The code is:


```css
td, th {
  padding: 15px;
  text-align: left;
  border: 1px solid grey;
}
```

I want to show you an important thing here. Say, we give a `background-color` of red, it'll override the style of `<th>` tag, that we defined earlier. This is how CSS works, as the last tag will take precedence over the earlier styles. It's good to be familiar with this behavior.

```css
th {
  background-color: black;
  color: white;
}

td, th {
  padding: 15px;
  text-align: left;
  border: 1px solid grey;
  background-color: red;
}
```

The output would be:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/Styling+Table+Rows+%23+514/realimage2.png)

To overcome this behavior, we're going to use a pseudo element called `tr-nth-child()`. This tag will help us select a particular item. If you see, this tag works like a function, so we can pass a specific row as its parameter. In this case, I'm going to pass the word `even` to this function, so it'll apply this style only for the even rows. This is the best way to implement alternate styles for every row, something you'll see commonly in many sites. Here, I'm going to give a background color of brown and a text color of white.

The code is:

```css
tr:nth-child(even)  {
  background-color: brown;
  color: white;
}
```

and the output is:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/Styling+Table+Rows+%23+514/image2.png)

This way, the earlier style of `<th>` is maintained, and at the same time, the different tables have a dynamic color.

One thing to keep in mind is our table header is the first row, and this is why CSS skips applying the new style to this row.

Also, there is a significant difference based on the order. `<th>` is more specific as it applies to a particular element inside a row, whereas `<tr>` is less specific as it applies to the entire row. This is why the style in `<th>` takes precedence.

I think this is pretty cool!



##Working with Column Spans

This guide walks through how to customize the column spans to alter the structure of a table.

In this video, we're going to talk about how to use the column span element.  As the name suggests, it'll allow us to have data that spans across different columns.

If you see our existing table, there is no heading for our "edit/delete" option, and this is kind of makes the table look incomplete.  Let's fix that.

Go to your HTML file, and under the `<th>` tags, add one more table header.  If you add an empty one, there'll be an empty header, which is ok. But, what we need is another one.
So, if you want to do it manually, add two empty `<th>` tags, and this will complete the table.

```html
<tr>
  <th>Name</th>
  <th>Average</th>
  <th>HRs</th>
  <th>RBIs</th>
  <th></th>
  <th></th>
</tr>
```

A better way is to use the column span element.  The code for that is:

```html
 <th colspan='2'></th>
```

This will create two columns, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/Working+with+Column+Spans+%23+515/image1.png)

I think this is a lot cleaner way to implement.

One more thing we need is totals, and this is a fairly common thing to have.  In fact, it can be particularly relevant for financial data.  You can implement this too, using `colspan`.

Let's now create a long column for the total, and for that, the code is:

```html
<tr>
  <td colspan = '6'>Totals...</td>
</tr>
```
This code should give a long total column, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/Working+with+Column+Spans+%23+515/image2.png)

This way, you'll have complete control over your table. You don't have to feel restricted while using data, as you can even use an entire row to display a specific information.  For example, you can have just the name of the player, and can combine the other rows together to display any information, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/Working+with+Column+Spans+%23+515/image3.png)

The corresponding code is:

```html
<tr>
  <td>Player XYZ</td>
  <td colspan="5">Did not play this year</td>
</tr>
```

This is a much better way of displaying the information than simply putting a value of zero in every column. In this sense, `colspan` gives you a ton of flexibility.



##How to Customize Row Sizes in HTML Tables

This lesson provides a step by step guide for customizing the size of rows in HTML tables.

This is the last video in the HTML tables section, and in this one, we're going to cover the row span.

You're already familiar with how to use column span, where you can customize your columns based on the data that needs to be displayed. A row span is also similar, except that it is applicable for rows. For example, if you have quite a few notes to add, row span would be a handy element.

Let's now add another element to a row, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/How+to+Customize+Row+Sizes+in+HTML+Tables+%23+516/image1.png)

Though this looks ok, it's  probably not the best way to implement it. Ideally, I'd want that element to take up all the rows underneath it.  For this, we'll use the row span element.

```html
<td rowspan = '6'>Updated Daily</td>
 ```

Now, our element looks much better.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/How+to+Customize+Row+Sizes+in+HTML+Tables+%23+516/image2.png)

Notice that there's no style that goes through it, and this is because this is a giant cell that takes up six rows Ideally, I'll have the `colspan` to 3 and `rowspan` to 7, so the entire table looks complete, like this:

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/How+to+Customize+Row+Sizes+in+HTML+Tables+%23+516/image3.png)

We can also customize the style for this element by giving it an ID. I'm going to call this ID `status`, but you can give whatever you want. Inside the selector, I want to center the text.

You can even call this class for any element that needs to be centered.  To do this, I'm going to remove the ID, and instead have a class called `center-table-text`, so I can use it for everything.  Next, I'll add this class for all our edit and delete content.

![](https://s3-us-west-2.amazonaws.com/devcamp-pictures/HTML+CSS+images/Guide+to+HTML+Tables/How+to+Customize+Row+Sizes+in+HTML+Tables+%23+516/image4.png)

I think it looks really professional now.
