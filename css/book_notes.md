## CSS selector
### Chained selector
Selector literally chained without any space or coma.
```css
h1  /* Simple selector: select all h1 */
div.vcard  /* 2 Chanined selector: select all div with class vcard */
div.vcard[title]  /* 3 Chained selector: select all div with class vcard and an attribute title */
```

### Selector group
Selector literally sit together separated with comma
```css
div, .vcard /* A selector group with two selectors: select all divs and all elements with vcard class */
```

### Simple selectors
#### Type selector
```css
div /* select elements div */
* { border:1px solid #400080;} /* Universal type selector: (*)select any element and set border 1 pixel*/
```

#### Attribute selector
```css
[foo] /* select elements who has attribute named foo */
[foo=bar] /* select elements who has attribute named foo, and value equals bar */
[foo~=bar] /* select elements who has attribute named foo, and value contains world bar, not abarrrrr */
[foo|=bar] /* select elements whos foo attribute contains a hyphen-separated list of words and the first word is exactly bar, for example, bar-1, bar-2-3-4-5, this is used to match  lang="zh-cn", lang="zh-hk" */

/* The following behaves just like regex */
[title^=bass] /* select elements with title attribute whose value begins with bass */
[title$=bass] /* select elements with title attribute whose value end with bass */
[title*=bass] /* select elements with title attribute whose value contains bass */
```



#### ID and class selector
```css
p#conductor /* select the p element whose id equals conductor */
#conductor /* select the element whose id equals to conductor, but since id is uinique amond all elements in a document, this is actually select the same p as above, iff there is a p with id conductor */
.orchestra /* select elements whose class attribute equals to orchestra */
```

#### Psuedo-classes
Pseduo-classes are a way to target elements that have a particular characteristic, which may not necessarily the element's attribute and value pairs. YOu use a colon **(:)** to delimit the beginning of a pseudo-class selector.

##### Hyperlinks
```css
a:link {color:blue;} /* select any anchor elements who is hyperlinks and set color to blue */
:link {color:blue;} /* select any link and set color to blue */
:visited {color:gray;} /* select any hyperlinks that have been visited, and set color to gray */
```

##### User intractions: Dynamic pseudo-classes
These apply to elements the user has acted upon in some way. In most cases, it turned to be a hyperlink.
```css
:active /* select element that are currently active, e.g., when a user clicks a hyperlink and has not yet released the mouse button or when user clicks a button on a form. Another example is by pressing a return or enter key on keyboard while the element has keyboard focus */
:focus /* select element which has focus. It make sense to group :hover and :focus together */
:hover /* select element which is hovering on */
```

##### :lang 
```css
:lang(zh) /* select element who has lang attribute with zh*/
[lang|=zh] /* same as above*/
```

##### Document fragment :target
```css
#conductor:target { font: 1.2em Helvetica, Sans-serif; } /* select conductor element when accessed via a link with a fragment identifier */
```

##### First or last element
```css
div h2:first-child /* first h2 element within any div */
body > :last-child /* very last child of body element */
:first-child /* match all elements that are 1st children of their parents */
tr:last-child td:first-child /* match all the 1st table cell in the last roe of any tables */
```