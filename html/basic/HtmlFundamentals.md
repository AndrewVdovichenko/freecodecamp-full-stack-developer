# Html Fundamentals

## What are Div Elements and When Should You Use Them?

The `div` element is used as a container to group other elements.

Here is an example of a `div` element.

```html
<div>
  <p>Example paragraph element.</p>
</div>
```

You will mainly use the `div` element when you want to group HTML elements that will share a set of CSS styles. You will learn more about CSS in future lessons and workshops.

Even though the `div` element is commonly used in real world codebases, you should be careful not to overuse it. There are times when another element would be more appropriate.

For example, if you wanted divide up your content into sections, then the `section` element would be more appropriate than a `div` element.

```html
<section>
  <h2>Mammals</h2>
  <p>Mammals are warm-blooded animals with fur or hair. Most give birth to live young.</p>
  <ul>
    <li>Lion</li>
    <li>Elephant</li>
    <li>Dolphin</li>
  </ul>
</section>
```

The `section` element has semantic meaning over the `div` element which is not semantic. Semantics are the meaning of words or phrases in a language. In HTML, which is a language, elements have their own semantic meaning too. So, this means if you use a `section` element, the browser will pick up its semantic meaning and understand to treat this as a section - on desktops, mobiles, you name it.

## What Are IDs and Classes, and When Should You Use Them?


The `id` attribute adds a unique identifier to an HTML element.

Here is an example of an `h1` element with an `id` of `title`.
```html
<h1 id="title">Movie Review Page</h1>
```
You can reference the `id` name of `title` within your JavaScript or CSS. Here's a CSS example referencing the `id` of `title` to change the text color to red.

```css
#title {
  color: red;
}
```

The hash symbol (`#`) in front of `title`, tells the computer you want to target an `id` with that value. `id` names should not be used more than once, and they should always be unique. Another thing to note about `id` values, is that they cannot have spaces in them. Here is an example of applying the words `main` and `heading` to an `id` attribute value:

```html
<h1 id="main heading">Main heading</h1>
```

Browsers will see this space as part of the `id` which will lead to unwanted issues when it comes to styling and scripting. `id` attribute values should only contain letters, digits, underscores, and dashes.

In contrast to the `id` attribute, the `class` attribute value does not need to be unique and can contain spaces.

Here is an example of applying a class called `box` to a `div` element.
```html
<div class="box"></div>
```
If you wanted to add multiple class names to an element, you can do so by separating the names by a space. Here is an updated example applying multiple classes to a `div` element.
```html
<div class="box red-box"></div>
```
```css
.box {
  width: 100px;
  height: 100px;
}

.red-box {
  background-color: red;
}
```

So, to recap, when should you use an `id` versus a `class`? Classes are best used when you want to apply a set of styles to many elements. If you want to target a specific element, it is best to use `id` because those values need to be unique.

## What Are HTML Entities, and What Are Some Common Examples?

An HTML entity, or character reference, is a set of characters used to represent a reserved character in HTML.

Let's say you wanted to display the text `This is an <img/> element` on the screen. If you use the code currently in the editor, it won't display the desired result. Even if you added `src` and `alt` attributes to the example, it would show an image in the middle of the paragraph. Not the desired result.

```html
<p>This is an <img /> element</p>
```

When the HTML parser sees the less than (`<`) symbol followed by an HTML tag name, it interprets that as an HTML element. That is why you are not getting the desired result of `This is an <img/> element` on the screen.

To fix this issue, you can use HTML entities. Here is an updated example using the correct HTML entities for the less (`<`) than and greater than (`>`) symbols. Now you should see `This is an <img/> element` on the screen.

Try adding a `&lt;p&gt;learning is fun&lt;/p&gt;` below the paragraph element. You should see `<p>learning is fun</p>` on the screen.

```html
<p>This is an &lt;img /&gt; element</p>
```

These types of character references are known as named character references. Named references start with an ampersand sign (`&`) and end with a semicolon (`;`). By using a named character reference, the HTML parser will not confuse this with an actual HTML element.

Another type of character reference would be the decimal numeric reference. This character reference starts with an ampersand sign and hash symbol (`#`), followed by one or more decimal digits, followed by a semicolon.

Here is an example of using the decimal numeric reference for the less than symbol.

You can use `&#169;` for the copyright symbol and `&#174;` for the trademark symbol.

```html
&#60;
```

The last type of character reference would be the hexadecimal numeric reference. This character reference starts with an ampersand sign, hash symbol, and the letter `x`. Then it is followed by one or more ASCII hex digits and ends with a semicolon.

Here is an example of using the hexadecimal numeric reference for the less than symbol.

You can use `&#x20AC;` for the euro symbol and `&#x03A9;` for the Greek capital letter Omega symbol.

```html
&#x3C;
```

## What Is the Role of the Script Element in HTML, and How Can It Be Used to Link to External JavaScript Files?

The `script` element is used to embed executable code. Most developers will use this to execute JavaScript code. JavaScript is used to add interactivity to your web pages. Common examples of using JavaScript include interactive games, image sliders, and dynamic forms that validate user input in real-time.

Here is an example of using the `script` element in an HTML document. Remove the `//` from in front of the `alert("Welcome to freeCodeCamp");` and you should see an alert pop up.

```html
<body>
  <script>
    // alert("Welcome to freeCodeCamp");
  </script>
</body>
```

While you can technically write all of your JavaScript code inside the `script` tags, it is considered best practice to link to an external JavaScript file instead. Here is an example of using the `script` element to link to an external JavaScript file:

```html
<script src="path-to-javascript-file.js"></script>
```

The `src` attribute is used here to specify the location for that external JavaScript file. `src` stands for "source". The reason why it is not encouraged to place all of your JavaScript inside the HTML document is because of separation of concerns. Separation of concerns is a design principle where you separate your programs into distinct sections and have each section address a separate concern. In this case, we want to separate our JavaScript code from our HTML code.
