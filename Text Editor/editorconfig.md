# EditorConfig

Nowadays many editors are support `.editorconfig` file to control base editing configs.

## How to use

Create file `.editorconfig` under your project root folder.
And put necessary config you need.

## Selectors

### Elements

```
*               match any character except /
**              match any character
?               match any single character
[abc]           match any single character listed in []
[!abc]          match any single character not listed in []
{jpg,png,gif}   match any case in {}
```

### Match sample

```
[*]                 global selector, normally this is the first one to define things in global level
[*.php]             match all PHP files in root folder
[**.js]             match all JS files in project
[**.{md,markdown}]  match all Markdown files
```


## Configs

```
charset                  = utf-8
indent_style             = space|tab
indent_size              = 4|tab
tab_width                = 4            (if indent_size set, no need to specify this again)
end_of_line              = lf|crlf|cr   (Unix, DOS, Mac)
insert_final_newline     = true|false
trim_trailing_whitespace = true|false
insert_final_newline     = true|false
max_line_length          = 80
```
