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

[ ] OK
[x] ok
