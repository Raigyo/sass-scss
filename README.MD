# SASS & SCSS: overview

*March 2020*

> 🔨 Training from Udemy
'[SASS & SCSS : la formation ULTIME](https://www.udemy.com/course/sass-scss-la-formation-ultime/)'.

![sass logo](readme-img/sass-logo.png)

## SASS: Syntacticaly Awesome Style Sheets

- concise syntax: no curly braces '{}' or semicolons ';'
- more easy to read

## SCSS: Sassy Cascading Style Sheets

- written like CSS
- precise syntax, force to write clearly
- integration/refactoring easier into an existing site using CSS
- future base for CSS specs? (for instance variables)

=> we can choose the syntax used with Sass preprocessor: '.sass' OR '.scss'

=> syntax used in the following exemples is Sassy Cascading Style Sheets / '.scss'

=> but it will be the same principle with '.sass' files excepted for the syntax

![My Sassy Cascading Style Sheets](readme-img/my-sassy.jpg)

## Installation of SASS preprocessor:

- Install Ruby: `sudo apt-get install ruby-full`
- Install SASS (a 'gem' in Ruby): `sudo gem install sass`
- Test: `sass --version`
- or with [scout-app.io](scout-app.io) but not recommended for an easy use

## Activate sass:

- In project, use relative path: `sass sass/default.scss css/default.css`
(or any other name for the scss/css. It's better to use the same for the two versions)

Sass will create the rendered css in 'css/default.css'. It will also add 'default.css.map'

## Automatic processing/watch:

- `sass --watch sass/default.scss:css/default.css`

Otherwise you will have to relaunch the command `sass sass/default.scss css/default.css`
to regenerate the '.scss' file.

## Comments with sass/scss:

- // Comment: not rendered by sass in css but still in sass/scss file
(so take care of what you write!)
- /\* Comment: rendered by sass in css \*/

## Variables

Exemple:

```
$primaryColor:purple;

header {
    background-color: $primaryColor;
}

```

## Operations:

- additions and subtractions (ex: `padding: 10px + 2px;` or `padding: 10px - 2;`)
- strings and concatenation
- multiplications and divisions (ex: `15px * 15` but not `15px / 5px`)

## Nesting

Exemple css:

```
footer {
    padding: 50px;
    background-color: $primaryColor;
}

footer span {
    color: #ffffff77;
}
```

Using scss (it will be rendered as if it was written in usual css):

```
footer {
    padding: 50px;
    background-color: $primaryColor;

    span {
        color: #ffffff77;
    }
}
```

## Current Selector '&' (= parent value )

Exemple with  css:

```
span {
    color: #ffffff77;
}

span:hover {
    text-decoration: underline;
}
```

Using scss (it will be rendered as if it was written in usual css):

```
    span {
        color: #ffffff77;

        &:hover {
            text-decoration: underline;
        }
    }
```

## Importation

To import scss into an another scss without rendering it in 'css'
(for instance if you don't need or want to import the css file a 'html' file):

Use the underscore '_' before the name and use '@' to import the file in '.scss'

Exemple for a new css, 'header':

```
css
-- default.css
-- default.css.map

sass
-- _header.scss
-- default.scss
```

In 'default.scss' import the '_header.scss" with `@import 'header';`
or with '.sass' files `@import header`.

For instance:

```
$primaryColor:purple;

@import 'header';

body {
    background-color: #ceaf26;
}
```

Of course we have to import it after the variables declaration
so you could use variable in the children scss...

## Inheritance and bloc of properties

We can declare a *bloc of properties* using Sass. For that we use '%'.

**Before using sass**:

HTML:

```
    <div class="alert alert-green">
      Green box
    </div>

    <div class="alert alert-red">
      Red box
    </div>
```

Css:

```
.alert {
    padding: 15px;
    border: 1px solid #ccc;
    color: white;
}

.alert-green {
    background-color: green;
}

.alert-red {
    background-color: red;
}

```

=> Inheritence is managed in html file!

**With Sass**:

HTML:

```
    <div class="alert-green">
      Green box
    </div>

    <div class="alert-red">
      Red box
    </div>
```

Scss:

```
%alert {
    padding: 15px;
    border: 1px solid #ccc;
    color: white;
}

.alert-green {
    @extend %alert;
    background-color: green;
}

.alert-red {
    @extend %alert;
    background-color: red;
}

```

=> Inheritance is managed in Scss!

=> If a bloc of properties is not called in a class, it's not rendered by Sass.



## Useful links

- [SASS & SCSS : la formation ULTIME](https://www.udemy.com/course/sass-scss-la-formation-ultime/)
- [SCSS: Sassy Cascading Style Sheets](https://sharkcoder.com/tools/scss)
- [CSS with superpowers](https://marksheet.io/sass.html)
- []()
- []()
- []()
- []()