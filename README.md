[![npm](http://img.shields.io/npm/v/consolate.svg)](https://www.npmjs.org/package/consolate)
[![travis](https://travis-ci.org/rollercodester/consolate.svg?branch=master)](https://travis-ci.org/rollercodester/consolate)
[![Dependency Status](https://david-dm.org/rollercodester/consolate.svg)](https://david-dm.org/rollercodester/consolate)

# consolate
#### Customize your Node.JS console like a dignitary.
Easily create intuitive log functions on the console object&mdash;even override built-in console functions (error, info, warn, etc.) And while you're at it, feel free to easily define colors, prefixes, and bullets that can automatically animate [cli-cursors](https://www.npmjs.com/package/cli-spinners).

![examples/6-cicd-pipeline.js](https://cloud.githubusercontent.com/assets/1450389/23842310/a584cdfc-0770-11e7-8969-f2d6659ca41a.gif)

## Index

* [Examples](#examples)
	* [Super-simple Custom Console Method](#example1)
	* [Overriding Built-in Console Methods](#example2)
	* [Animated vs Static Bullets](#example3)
	* [Smart Log Argument Handling](#example4)
	* [Apollo 11](#example5)
	* [CI/CD Pipeline Console](#example6)
* [API Reference](#api)

<a name="examples"></a>

## Examples

<h3><a name="example1" href='https://github.com/rollercodester/consolate/blob/master/examples/1-simple-custom-method.js'>Super-simple Custom Console Method</a></h3>

![examples/1-simple-custom-method.js](https://cloud.githubusercontent.com/assets/1450389/23828435/20fe2f50-0686-11e7-962f-fbf2702ea259.gif)

```javascript
var consolate = require('consolate')

consolate.init({
   arrow: {
      color: consolate.colors.cyan,
      prefix: {
         chars: '>>>>>----->',
         color: consolate.colors.lightCyan
      }
   }
})

console.arrow('My customized "arrow" log method!')

setTimeout(() => {
	console.arrow('Just think of the possibilities :-)')
}, 1500)

setTimeout(() => {
	console.arrow('And we haven\'t even scratched the surface.')
}, 3000)

setTimeout(() => {
	console.arrow('Okay, one more time before moving on.')
	console.log()
}, 4500)
```

<h3><a name="example2" href='https://github.com/rollercodester/consolate/blob/master/examples/2-console-overrides-on-built-in-methods.js'>Overriding Built-in Console Methods</a></h3>

![examples/2-console-overrides-on-built-in-methods.js](https://cloud.githubusercontent.com/assets/1450389/23828470/7610d2f8-0687-11e7-8410-fdf2b567775a.gif)


<h3><a name="example3" href='https://github.com/rollercodester/consolate/blob/master/examples/3-animated-and-static-bullets.js'>Animated vs Static Bullets</a></h3>

![examples/3-animated-and-static-bullets.js](https://cloud.githubusercontent.com/assets/1450389/23828520/e8a89fd4-0688-11e7-9c95-aa3959920f46.gif)


<h3><a name="example4" href='https://github.com/rollercodester/consolate/blob/master/examples/4-smart-log-argument-handling.js'>Smart Log Argument Handling</a></h3>

![examples/4-smart-log-argument-handling.js](https://cloud.githubusercontent.com/assets/1450389/23831679/bd7c44d6-06e3-11e7-9e8c-087b0b996a75.gif)


<h3><a name="example5" href='https://github.com/rollercodester/consolate/blob/master/examples/5-apollo-11.js'>Apollo 11</a></h3>

![examples/5-apollo-11.js](https://cloud.githubusercontent.com/assets/1450389/23831850/6751c74a-06e6-11e7-8340-66e53124a7c0.gif)


<h3><a name="example6" href='https://github.com/rollercodester/consolate/blob/master/examples/6-cicd-pipeline.js'>CI/CD Pipeline Console</a></h3>

![examples/6-cicd-pipeline.js](https://cloud.githubusercontent.com/assets/1450389/23842310/a584cdfc-0770-11e7-8969-f2d6659ca41a.gif)


<a name="api"></a>

## API Reference
<a name="module_consolate.init"></a>

## consolate.init(options)
The initialization function that must be called to enable consolate.

**Kind**: static method of <code>[consolate](#module_consolate)</code>  

| Param | Type | Description |
| --- | --- | --- |
| options | <code>consolateOptions</code> | (or string) Options object with values that drive consolate behavior OR this parameter can be a filepath to options yaml file. If options is not provided, then a default options file consolate.yml will be searched for in working directory. See example #6 (examples/6-cicd-pipeline.js) for an example options yaml file. |

<a name="module_consolate..colors"></a>

## consolate~colors : <code>enum</code>
Color representations of ANSI output text codes that consolate supports.

**Kind**: inner enum of <code>[consolate](#module_consolate)</code>  
**Read only**: true  
**Properties**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| reset | <code>number</code> | <code>0</code> | Not a color, per se...rather used to reset the active color back to default |
| default | <code>number</code> | <code>39</code> | The default color configured by your terminal |
| black | <code>number</code> | <code>30</code> |  |
| red | <code>number</code> | <code>31</code> |  |
| green | <code>number</code> | <code>32</code> |  |
| yellow | <code>number</code> | <code>33</code> |  |
| blue | <code>number</code> | <code>34</code> |  |
| magenta | <code>number</code> | <code>35</code> |  |
| cyan | <code>number</code> | <code>36</code> |  |
| lightGray | <code>number</code> | <code>37</code> |  |
| darkGray | <code>number</code> | <code>90</code> |  |
| lightRed | <code>number</code> | <code>91</code> |  |
| lightGreen | <code>number</code> | <code>92</code> |  |
| lightYellow | <code>number</code> | <code>93</code> |  |
| lightBlue | <code>number</code> | <code>94</code> |  |
| lightMagenta | <code>number</code> | <code>95</code> |  |
| lightCyan | <code>number</code> | <code>96</code> |  |
| white | <code>number</code> | <code>97</code> |  |

<a name="module_consolate..restore"></a>

## consolate~restore
Restores the console object back to its native state by removing all consolate modifications.

**Kind**: inner constant of <code>[consolate](#module_consolate)</code>  
<a name="module_consolate..consolateOptions"></a>

## consolate~consolateOptions : <code>Object</code>
The consolate options object that defines output methods and their respective settings and/or overrides existing log methods and their behavior.

**Kind**: inner typedef of <code>[consolate](#module_consolate)</code>  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| key | <code>string</code> | The name of an output method (built-in or user-defined), which consolate will use to create a log method (of same name) on the console object. |
| value | <code>outputMethodSettings</code> | The settings to apply to the respecive output method. |

<a name="module_consolate..outputMethodSettings"></a>

## consolate~outputMethodSettings : <code>Object</code>
An object that represents the settings for the output method that has the same name as this object's key.

**Kind**: inner typedef of <code>[consolate](#module_consolate)</code>  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| inPlace | <code>boolean</code> | Specifies that when a series of calls are made for this output method, all subsequent output will be rendered on the same line after the initial call—in effect overwriting the previous console output. |
| color | <code>colors</code> | The color to use for the output text. |
| prefix | <code>prefix</code> | The prefix option (if any) to use for this output method. |
| bullet | <code>bullet</code> | The bullet option (if any) to use for this output method. |

<a name="module_consolate..prefix"></a>

## consolate~prefix : <code>Object</code>
Specifies preferences (if any) for including an automatic prefix to all console output for an output method.

**Kind**: inner typedef of <code>[consolate](#module_consolate)</code>  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| chars | <code>string</code> | One or more characters to use as the prefix. |
| color | <code>colors</code> | The color to use for the prefix text. |
| leftPadding | <code>number</code> | The number of spaces to pad on the left side of the prefix. |
| rightPadding | <code>number</code> | The number of spaces to pad on the right side of the prefix. |

<a name="module_consolate..bullet"></a>

## consolate~bullet : <code>Object</code>
Specifies preferences (if any) for including an automatic left-aligned bullet to all console output for an output method.

**Kind**: inner typedef of <code>[consolate](#module_consolate)</code>  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| cliSpinner | <code>string</code> | For an animated bullet, this is the spinner name to use per the [cli-spinners](https://www.npmjs.com/package/cli-spinners) library. Note: The animation will continue until a different output method is called, which will then overwrite the animation output, thus stopping and clearing it. |
| chars | <code>string</code> | For a static (non-animated) bullet, this is one or more characters to use as the bullet. This property is ignored if cliSpinner is specified. |
| color | <code>colors</code> | The color to use for the bullet text. |
| leftPadding | <code>number</code> | The number of spaces to pad on the left side of the bullet. |
| rightPadding | <code>number</code> | The number of spaces to pad on the right side of the bullet. |




