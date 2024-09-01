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

  > Don't write spaghetti code
</details>

## HTML Formatting

<details>
  <summary>Remember about correct indentation between parent and child elements</summary>

  > Each level of nesting, including text, contained inside the element, requires a 2-space offset.
  > Also blank lines shouldn't be between parent and child elements.

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

  > If the HTML element has long attribute values or the number of attributes is more than 2 - start each one,
  including the first, on the new line with a 2-space indentation related to the tag.
  The tag’s closing bracket should be on the same level as the opening one.

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

  > Just follow BEM

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
  <summary>DON'T reset default styles in classes if you can make it by modifying a tag</summary>
  
  > You can reset default styles like this:
  
  ```css 
  body {
    margin: 0;
  }
  ```
</details>

<details>
  <summary>DON'T use hardcoded values!!!</summary>

  > It is bad practice, you will be punished 😈

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

  > Remember about reusing styles

  ```scss
  @mixin on-tablet {
    @media (...) {
      @content;
    }
  }
  ```
</details>

<details>
  <summary>Write styles with this template</summary>

  > It makes tour code more readable

  Template:
  ```
  .class {
    position;
    block model;
    text customization;
    borders, animatiojns and other;
  ```

  **Warning**: use styles **logicaly** and **use blank lines**.

  BAD example
  ```css
  .class {
    display: flex;
    gap: 15px;
    position: absolute;
    text-size: 20px;
    top: 10px;
    font-weight: 700;
    border-radius: 5px;
    color: #000;
    border: 1px solid #000;
    background-color: #fff;
    padding: 10px;
    box-sizing: border-box;
  ```

  GOOD example
  ```css
  .class {
    position: absolute;
    top: 10px;

    box-sizing: border-box;
    display: flex;
    gap: 15px;
    padding: 10px;

    text-size: 20px;
    font-weight: 700;
    color: #000;

    background-color: #fff;
    border-radius: 5px;
    border: 1px solid #000;
  ```
  
</details>

## JavaScript Formatting

<details>
  <summary>USE BLANK LINES. Make your code readable</summary>

  BAD example
  ```javascript
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
```javascript
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
  ```javascript
  const func = (...args) => {
    for (const arg of args) {
      if (!arg) return false;
    };

    return true;
  }
  ```

  GOOD example
  ```javascript
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
  ```javascript
  let a = 1
  
  const b = { c: 1, d: 2 }
  ```

  GOOD example
  ```javascript
  let a = 1;
  
  const b = {
    c: 1,
    d: 2,
  }
  ```
</details>

<details>
  <summary>Prefer use <code>const</code> instead a <code>let</code>. Make names suitable</summary>

  BAD example
  ```javascript
  let a = 1
  
  const b = { c: 1, d: 2 }
  ```

  GOOD example
  ```javascript
  const FILTER_INDEX = 1;
  
  const b = {
    c: 1,
    d: 2,
  }
  ```
</details>

<details>
  <summary>Write global constants in <b>upper snake case</b> </summary>

  > Remember constants in the `Mats` module

  BAD example
  ```javascript
  const filterIndex = 1
  const sortByName = 'name';
  ```

  GOOD example
  ```javascript
  const FILTER_INDEX = 1;
  const SOTR_BY_NAME = 'name';
  ```
</details>

<details>
  <summary><b>ALWAYS</b> add brackets for <b>arrow</b> functions</summary>

  > Even if the argument only one

  BAD example
  ```javascript
  const func = arg => { ...some logic };
  ```

  GOOD example
  ```javascript
  const func = (arg) => { ...some logic };
  ```
</details>

## TypeScript Formatting
<details>
  <summary>Avoid using enums. It is not so important, but prefer to use the next construction</summary>

  > Enums have some issues. More information [here](https://thoughtbot.com/blog/the-trouble-with-typescript-enums)

  ```typescript
  const FILTER = {
    BY_NAME: 'name',
    BY_PRICE: 'price',
  } as const;
  ```
</details>

<details>
  <summary>Try to avoid complicated  types in functions</summary>

  > Better write type or interface

  BAD example
  ```typescript
  const func = ({ a, b }: { a: string, b: string}): string = { ...some logic };
  ```

  GOOD example
  ```typescript
  interface FuncProps {
    a: string;
    b: string;
  }

  const func = ({ a, b }: FuncProps): string = { ...some logic };
  ```
</details>

<details>
  <summary><b>NEVER</b> use <code>any</code> type</summary>

  > It is bad practice, you will be punished 😈

</details>

<details>
  <summary>Don't forget about <code>!</code> and <code>?</code> operators</summary>

  > Sometimes it helps to write less code with the same logic
</details>

## React Components Formatting
<details>
  <summary>Write components with arrow functions</summary>

  ```jsx
  const Component = () => <></>
  ```
</details>

<details>
  <summary>Always apply types to your component</summary>

  ```jsx
  import { FC } from 'react';

  interface Props {
    a: string;
    b: (c: string) => void;
  }

  const Component: FC<Props> = ({ a, b }) => <></>;
  ```
</details>

<details>
  <summary>Always use reexports</summary>

  > Take care of other developers and yourself
</details>

## Frameworks

<details>
  <summary>Don't forget about our code style and modification presetuped linter and prettier rules</summary>

  > Link to our [codestyle](https://github.com/BinoviTeam/prettier-settings)
</details>

<details>
  <summary>Always change essentials rules to recommended</summary>

  ```javascript
  // Vue 3 presetuped ESLint rules

 
  /* eslint-env node */
  require('@rushstack/eslint-patch/modern-module-resolution');
  
  module.exports = {
    root: true,
    extends: [
      'plugin:vue/vue3-recommended', ⬅️⬅️⬅️
      'eslint:recommended', ⬅️⬅️⬅️
      '@vue/eslint-config-typescript',
      '@vue/eslint-config-prettier/skip-formatting',
    ],
    parserOptions: {
      ecmaVersion: 'latest',
    },
  };
  ```
</details>
