# Codestyle. Read this, its important!!!

## Main concepts Formatting

<details>
  <summary>Use <b>2 spaces</b> for indentation in your file (not a <code>tab</code> character)</summary>
  
  <p>It belongs to this languages: <b>HTML</b>, <b>CSS</b>, <b>JavaScript</b>, <b><TypeScript/b></p>

  <ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
    <li>TypeScript</li>
  </ul>

  > Make sure your formatting will look the same everywhere!

  GOOD Example:

  ```html
  <body>
    <content />
  </body>
  ```

  ```css
  * {
    box-sizing: border-box;
  }
  ```

  ```javascript
  const indent = {
    key: value,
  };
  ```

</details>

<details>
  <summary>Lines of code have <code>80</code> chars max</summary>
</details>

## HTML Formatting

<details>
  <summary>Remember about correct indentation between parent and child elements</summary>

  > Each level of nesting, including text, contained inside the element, requires 2-space offset.
  > Also blank line shouldn't be between parent and child elements.

  GOOD example

  ```html
  <body>
    <div>
      <p>Awesome text</p>
    </div>
  </body>
  ```

  BAD example

  ```html
  <body>
    <div>
      <p>Awesome text</p>
    </div>
  </body>
  ```

</details>

<details>
  <summary>Add empty lines between multiline sibling blocks of HTML</summary>

  > To add some "air" and simplify reading. But don't add them between parent and child elements.

  GOOD Example

  ```html
  <ul>
    <li class="nav__item">
      <a href="#home">Home</a>
    </li>

    <li class="nav__item">
      <a href="#shop">Shop</a>
    </li>

    <li class="nav__item">
      <a href="#contacts">Contacts</a>
    </li>
  </ul>
  ```

  BAD Example

  ```html
  <ul>
    <li class="nav__item">
      <a href="#home">Home</a>
    </li>
    <li class="nav__item">
      <a href="#shop">Shop</a>
    </li>
    <li class="nav__item">
      <a href="#contacts">Contacts</a>
    </li>
  </ul>
  ```

</details>

<details>
  <summary>Keep your attributes correctly formatted</summary>

  > If the HTML-element has long attribute values or number of attributes is more than 2 - start each one,
  including the first, on the new line with 2-space indentation related to tag.
  Tag’s closing bracket should be on the same level as opening one.

  GOOD Example
  ```html
  <input
    type="text" 
    name="surname" 
    id="surname"
    required
  >
  ```

  BAD Examples
  ```html
  <input type="text" name="surname" 
         id="surname" required>

  <input type="text" 
         name="surname" 
         id="surname"
         required>

  <input
  type="text" 
  name="surname" 
  id="surname"
  required>

  <input
    type="text" 
    name="surname" 
    id="surname"
    required>
  ```
</details>

## HTML Content

<details>
  <summary>Use semantic tags where possible</summary>

  > Like `header`, `section`, `article`, `p`. It improves your page SEO and helps screen readers. `div` and `span` does not have any meaning
</details>

<details>
  <summary> <code>alt</code> attribute should describe the image content</summary>


  GOOD example
  ```html
  <img alt="Samsung Galaxy S22 2022 8/128GB Green" />
  ```

  REALLY BAD example
  ```html
  <img alt="image" />
  ```

  STILL BAD example
  ```html
  <img alt="phone" />
  ```
</details>

<details>
  <summary>Class names represent the meaning of the content (not the styles or tag names)</summary>

  GOOD example
  ```html
  <nav class="nav">
    <ul class="nav__list">
      ...
      <li class="nav__item">
        <a href="#apple" class="nav__link">Apple</a>
      </li>
    </ul>
  </nav>
  ```

  BAD example
  ```html
  <nav class="no-padding">
    <ul>
      ...
      <li class="li">
        <a href="#apple" class="a-last-no-decoration">Apple</a>
      </li>
    </ul>
  </nav>
  ```
</details>

## CSS Formatting

## JavaScript Formatting

## Variables Formatting

## Functions Formatting

## Components Formatting

## TypeScript Formatting
