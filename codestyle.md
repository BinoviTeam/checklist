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

  > Just folow BEM

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

<details>
  <summary>DON'T use universal selector <code>*</code> for reset the styles</summary>
  
  > Use this selector only for normalizing styles

  ```css
  * {
    box-sizing: border-box;
  }
  ```
</details>

<details>
  <summary>DON'T reset default styles in classes if you can make it by modifacating a tag</summary>
  
  > You can reset default styles like that:
  
  ```css 
  body {
    margin: 0;
  }
  ```
</details>

<details>
  <summary>DON'T use hardcoded values!!!</summary>

  > Its bad practice, you will bee punished

  BAD example
  ```scss
  .text {
    color: #fff;
  ```

  GOOD example
  ```scss
  // variables.scss
  
  :root {
    font-size: 12px;
    font-weigth: 600;
  }
  
  $text-color: #fff;
  ```

  ```scss
  // text.scss

  .text {
    color: $text-color;
  ```
</details>

<details>
  <summary>If you use <b>SCSS</b>, write mixins and style documentation</summary>

  > Remenber about reusing styles

  ```scss
  @mixin on-tablet {
    @media (...) {
      @content;
    }
  }
  ```
</details>

## JavaScript Formatting

<details>
  <summary>USE BLANK LINES. Make you code readable</summary>

  BAD example
  ```js
  const func = (...args) => {
    const arr = [];
    for (const arg of args) {
      if (arg) {
        arr.push(arg);
      };
    };
    return arr;
  }
```

GOOD example
```js
  const func = (...args) => {
    const arr = [];

    for (const arg of args) {
      if (arg) {
        arr.push(arg);
      };
    };

    return arr;
  }
```
</details>

<details>
  <summary>DON'T return a value in the same line with condition</summary>

  > Use curve brackets

  BAD example
  ```js
  const func = (...args) => {
    for (const arg of args) {
      if (!arg) return false;
    };

    return true;
  }
  ```

  GOOD example
  ```js
  const func = (...args) => {
    for (const arg of args) {
      if (!arg) {
        return false;
      };  
    };
  
    return true;
  }
  ```
</details>

<details>
  <summary>Always use semicolons and commas</summary>

  > Presetupped Prettier and ESLinter [included](https://github.com/BinoviTeam/prettier-settings) 

  BAD example
  ```js
  let a = 1
  
  const b = { c: 1, d: 2 }
  ```

  GOOD example
  ```js
  let a = 1;
  
  const b = {
    c: 1,
    d: 2,
  }
  ```
</details>

## Variables Formatting

## Functions Formatting

## Components Formatting

## TypeScript Formatting
