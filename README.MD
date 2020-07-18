# SASS & SCSS

*March 2020*

> 🔨 Training from Udemy
'[SASS & SCSS : la formation ULTIME](https://www.udemy.com/course/sass-scss-la-formation-ultime/)'.

![sass logo](readme-img/sass-logo.png)

## SASS: Syntacticaly Awesome Style Sheets

- concise syntax: no curly braces '{}' or semicolons ';'
- easy to read

## SCSS:

- written like CSS
- precise syntax, force to write clearly
- integration easier into an existing site using CSS
- future base for CSS4?

=> we can choose the syntax used with Sass preprocessor: '.sass' OR '.scss'

## Installation of SASS preprocessor:

- Install Ruby: `sudo apt-get install ruby-full`
- Install SASS (a 'gem' in Ruby): `sudo gem install sass`
- Test: `sass --version`
- or with: scout-app.io

## Activate sass:

- In project, use relative path: `sass sass/default.scss css/default.css`

## Automatic processing/watch:

- `sass --watch sass/default.scss:css/default.css`

## Comments with sass/scss:

- //Comment: not rendered by sass in css but still in sass
- /*Comment: rendered by sass in css*/

## variables

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