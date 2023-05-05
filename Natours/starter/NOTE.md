### How to Compile a SCSS File?

##### 1. Install a compiler or a preprocessor (sass here).

```sh
npm install -g sass
```

##### 2. Add a field `compile:sass` in `"script"` of `package.json` file.

- This command will compile the 'sass/main.scss' file to 'css/style.css'.
- The flag `-w` means that watch the SCSS file for changes and automatically recompile it to CSS whenever changes are made to the SCSS file.

```json
{
  "name": "natours",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "compile:sass": "sass sass/main.scss css/style.css -w"
  },
  "author": "Logic",
  "license": "ISC",
  "devDependencies": {
    "sass": "^1.59.3"
  }
}
```

##### 3. Run the `"compile:sass"` script with npm

```sh
npm run compile:sass
```

### Implementing 7-1 CSS Architecture with SASS

7-1 CSS architecture is a popular way of organizing CSS files for large projects. The architecture consists of seven different folders and one main file to import all the other files.

It is designed to handler large multi-page websites or web apps

The seven folders in the 7-1 CSS architecture are:

1. base/: This folder contains styles for HTML elements such as typography, color palettes, and other basic styles.
2. components/: This folder contains styles for reusable UI components such as buttons, forms, cards, etc.
3. layout/: This folder contains styles for the overall layout of the page, such as grids, containers, and responsive design.
4. pages/: This folder contains styles that are specific to individual pages or sections of the website.
5. themes/: This folder contains styles for different themes or color schemes that the website may have.
6. utils/: This folder contains utility classes and helper styles, such as margin, padding, and positioning classes.
7. vendors/: This folder contains styles for third-party libraries or plugins that the website may use.

The main file, usually named styles.scss or main.scss, imports all of these folders in a specific order to ensure that the styles cascade correctly and efficiently.

### Responsive Design Principles and Layout Types

1. Fluid Layouts

- To allow webpage to adapt to the current viewport width (or even height)
- Use `%` (or `vh` / `vw`) unit instead of `px` for elements that should adapt to viewport (usually layout)
- Use `max-width` instead of `width`

2. Responsive Units

- Use `rem` unit instead of `px` for most lengths
- To make it easy to scale the entire layout down (or up) automatically

3. Flexible Images

- By default, images don't scale automatically as we change the viewport, so we need to fix that
- Always use `%` for image dimensions, together with the `max-width` property

4. Media Queries

- To change CSS styles on certain viewport widths (called breakpoints)

> **Attribute Selector**
> What is `[class^="col-"] {}` in `_grid.scss`?
>
> This is an attribute selector in CSS, specifically, it is a value selector that starts with `^=` and selects elements with an attribute value that begins with the specified value.
>
> For example, `[class^="col-"]` selects all elements that have a class attribute and whose value starts with col-. This selector is commonly used in grid systems to select column elements with a specific naming convention. For instance, in the Bootstrap grid system, the class attribute of column elements usually starts with col-, such as col-sm-6 representing a column that occupies half the width on small screens. Therefore, `[class^="col-"] `can be used to select all column elements and easily apply style rules to them.
>
> It is worth noting that attribute value selectors can use other symbols besides `^=`, such as `$=` for selecting elements with attribute values that end with the specified value, `*=` for selecting elements with attribute values that contain the specified value, and so on. These selectors can all be used to target elements with specific attribute values in practical development.

### Building the About Section

What we will learn in this lecture?

- Thinking about components
- How and why use utility classes
- How to use the `background-clip` property
- How to `transform` multiple properties simultaneously
- How to use the `outline-offset` property together with `outline`
- How to style elements that are not hovered while others are

#### -webkit-background-clip

We are using `-webkit-background-clip` to make `heading-secondary` to be a gradient background.

Here is an example that demonstrates how to apply the `-webkit-background-clip` property to a `div` element to make the background image only show in the text area:

```css
div {
  background-image: url("background.png");
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
}
```

In the code above, the background-image property specifies the background image to be used, and the background-clip and -webkit-background-clip properties specify that the background image is limited to the text area. By setting the text color to transparent, the background image is fully displayed in the text area.

Note that since the -webkit-background-clip property is a non-standard property, it may be deprecated or no longer supported in future browser versions. Therefore, when writing CSS code, it is recommended to avoid using private CSS properties to ensure code compatibility and maintainability.
