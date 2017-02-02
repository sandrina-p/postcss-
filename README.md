# postcss-ltr-rtl-detect

[PostCSS](https://github.com/postcss/postcss) plugin that detects properties in your CSS that influence LTR and RTL layouts and are not being generated by @mixins or another dynamic way.

**Properties detected:**  
`padding`, `padding-left`, `padding-right`, `margin`, `margin-left`, `margin-right`, `text-align`, `float`, `left`, `right`;

## Usage
All warnings are written to postcss `result.messages`. You'll need a tool to handle them, for example, [postcss-reporter](https://www.npmjs.com/package/postcss-browser-reporter).

```js

    postcss() {
        return [
            require('postcss-ltr-rtl-detect'),
            require('postcss-reporter'),
        ];
    }
```

### Options

```js

    /* activate units detection */
    postcss() {
        return [
            require('postcss-ltr-rtl-detect')({
                unitsDetect: true,
            }),
            require('postcss-reporter'),
        ];
    }

```

#### `propsMsg` (optional)
Warning shown when a propriety that affects the layout RTL vs LTR is found.  
**Type:** `string`  
**Default:** Consider using a variable.

#### `unitsDetect` (optional)
Detects properties that have `px`, `rem` or `em`.  
**Type:** `Bollean`  
**Default:** false


#### `unitsMsg` (optional)
Warning shown when a unit value is found (`unitsDetect: true` required).  
**Type:** `string`  
**Default:** Use a @mixin to support LTR vs RTL.


## Contribute
Any doubt or suggestion you may have feel free to create an issue on [github repo]().


## License
MIT Licence

## Change Log
**0.1.0** initial release
