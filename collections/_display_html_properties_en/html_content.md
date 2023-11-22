---
title: Content
section: specifics
propName: content
propPath: properties.content
scriptApiClass: Actor.Display.HtmlProperties
order: 7
---

Wildcardable
{: .label }

This property allows you to define the HTML content of the actor.

**For example :**

```html
<div style="background-color: lighblue;">
    <p>
        This is <i>a</i> <b>paragraph</b>.
    </p>
</div>
```
Result:
<div style="background-color: lighblue;">
    <p>
        This is <i>a</i> <b>paragraph</b>.
    </p>
</div>


> 💡 **TIP**<br>
> If it is possible to add CSS style with an HTML tag `<style>`, it is not possible to add Javascript code.
> For this, you have to use the events of the actor.


### Wildcardable

It is possible to place wildcards (e.g. {% raw %}`{{wildcardKey}}`{% endraw %}) in the content that will be replaced by the value of corresponding additional keys.


For example:

{% raw %}
```html
<div style="background-color: {{theColor}};">
    <p>
        This is a paragraph.
    </p>
</div>
```
{% endraw %}

An additional key `theColor` of type *color* will replace the wildcard with its value.



**To help you:**
The documentation on wildcards and their uses can be found [at this address]().
