<!-- prettier-ignore -->
# BEM : Block\_\_Element--Modifier

<http://getbem.com/>

<https://en.bem.info/methodology/>

<https://www.youtube.com/watch?v=er1JEDuPbZQ&ab_channel=DesignCourse>

is a methodology that helps you to create reusable components and code sharing in front-end development

## Block

Encapsulates a standalone entity that is meaningful on its own. While blocks can be nested and interact with each other, semantically they remain equal; there is no precedence or hierarchy. Holistic entities without DOM representation (such as controllers or models) can be blocks as well.

> `header`, `container`, `menu`, `checkbox`, `input`

**Naming**  
Block names may consist of Latin letters, digits, and dashes. To form a CSS class, add a short prefix for namespacing: `.block`

**HTML**  
Any DOM node can be a block if it accepts a class name.

> ```html
> <div class="block">...</div>
> ```

**CSS**

- Use class name selector only

- No tag name or ids

- No dependency on other blocks/elements on a page

> ```css
> .block { color: #042; }-
> ```

## Element

A part of a block that has no standalone meaning and is semantically tied to its block.

> `menu item`, `list item`, `checkbox caption`, `header title`

**Naming**  
Element names may consist of Latin letters, digits, dashes and underscores. CSS class is formed as block name plus two underscores plus element name: `.block__elem`

**HTML**  
Any DOM node within a block can be an element. Within a given block, all elements are semantically equal.

> ```html
> <div class="block">
>   ...
>   <span class="block__elem"></span>
> </div>
> ```

**CSS**

- Use class name selector only

- No tag name or ids

- No dependency on other blocks/elements on a page

Good

> ```css
> .block__elem {  color: #042;}
> ```

Bad

> ```css
> .block .block__elem {  color: #042;}
>       div.block__elem {  color: #042; }
> ```

## Modifier

A flag on a block or element. Use them to change appearance or behavior.

> `disabled`, `highlighted`, `checked`, `fixed`, `size big`, `color yellow`

**Naming**  
Modifier names may consist of Latin letters, digits, dashes and underscores. CSS class is formed as block’s or element’s name plus two dashes: `.block--mod` or `.block__elem--mod` and `.block--color-black` with `.block--color-red`. Spaces in complicated modifiers are replaced by dash.

**HTML**  
Modifier is an extra class name which you add to a block/element DOM node. Add modifier classes only to blocks/elements they modify, and keep the original class:

Good

> ```html
> <div class="block block--mod">...</div>
>   <div class="block block--size-big
>		 block--shadow-yes">...</div>
> ```

Bad

> ```html
> <div class="block--mod">...</div>>
> ``


**CSS**

Use modifier class name as selector:

> ```css
> .block--hidden { }
> ```

To alter elements based on a block-level modifier:s

> ```css
> .block--mod .block__elem { }
> ```

Element modifier:

> ```css
> .block__elem--mod { }
> ```


![github captions](logo)

![github captions](img/github_captions.jpg)

[logo]: img/github_captions.jpg "Github Captions"
