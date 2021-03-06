# smartwrap
Textwrap for javascript/nodejs. Correctly handles wide characters (宽字符) and emojis (😃). Automatically breaks long words.

## Why? 

I needed a javascript package to correctly wrap wide characters - which have a "length" property value of 1 but occupy 2 or more spaces in the terminal.

## Example Usages:

### Terminal:
```sh
npm i -g smartwrap
echo somestring you want to wrap | smartwrap --width=3 --paddingLeft=1
```

#### Output:
```
 so
 me
 st
 ri
 ng
 yo
 u
 wa
 nt
 to
 wr
 ap
```

## Node module:

```js
var Smartwrap = require('smartwrap');
var exampleText1 = '宽字符';
console.log(Smartwrap(exampleText1,{
  width: 2
}));
```
#### Output:
```
宽
字
符
```

## Options

```sh
  --minWidth      Never change this unless you are certin you are not using
                  wide characters and you want a column 1 space wide. Then
                  change to 1.                   [choices: 1, 2] [default: 2]
  --paddingLeft   Set the left padding of the output             [default: 0]
  --paddingRight  Set the right padding of the output            [default: 0]
  --splitAt       Characters at which to split input    [default: [" ","\t"]]
  --trim          Trim the whitespace from end of input       [default: true]
  --width, -w     Set the line width of the output (in spaces)
                                                     [required] [default: 10]
```

