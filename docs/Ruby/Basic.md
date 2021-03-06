#### Minimum Recommended Language

[<i class="fas fa-link">&nbsp;</i>Source](https://taxiforemail.com/code/minimum-viable-language/ 'Minimum Viable Language')

``` html
<module name="module1" label="Module with a headline">
 <span style="color:red;">
  <editable name="headline" label="Main Headline" hint="Please ensure you use sentence case only">Lorem ipsum</editable>
 </span>
</module>
```

#### The `<editable>` tag

Wrap an `<editable>` tag around the content you wish to make editable. The editable tag should be around the content but should not include any formatting. CMS recognises standard HTML tags and adds fields in the editor as necessary - you can wrap editable tags around text, links or images (or linked images if you're fancy).
Editable tags should not be nested within one another.
It's important to close the `</editable>` tag in a semantic way.


<!-- tabs:start -->

#### ** Text **

If you wrap an editable tag around text, that text becomes editable:

```html
<td style="font-size:18px; font-family:Helvetica, Arial, sans-serif; color:#111111">
 <editable name="headline" label="Main headline">
  Headline text
 </editable>
</td>
```

CMS will provide a text area for the editor to update the content.

#### ** Link **

A link is made editable by wrapping an `<editable>` tag around an `<a>` tag.

```html
<editable name="cta" label="CTA Button">
 <a href="http://www.taxiforemail.com">Find out more</a>
</editable>
```

#### ** Image **

An image is made editable by wrapping `<editable>` around an `<img>` tag.

```html
<editable name="heroimage" label="Hero Image">
 <img src="http://placekitten.com/200/300" height="200" width="300" alt="kittens!" style="display:block">
</editable>
```

CMS will provide fields for the image source, height, width and alt text. The editor will be able to upload images, or provide a url for the image location (image uploads may not be turned on for your organisation, but this doesn't affect how we code the template).

##### Linked images

If you wrap an editable tag around an `<a>` tag that contains (only) an `<img>`, then CMS will provide both the link and image fields, plus a button to remove the link if required.

#### ** Anything else **

If you wrap an editable tag around code that CMS doesn't understand, or multiples of the above (eg. Text and an image) then CMS will make all of that code editable in a paragraph field.

<!-- tabs:end -->



#### The Attributes `name`, `label` and `hint`

```html
<editable name="headline" label="Main Headline" hint="Please ensure you use sentence case only"></editable>
```

<!-- tabs:start -->

#### ** name= **

`name=` required

Every editable tag must have a `name=` attribute. This helps CMS when saving and retrieving content, and maps the content in the CMS database to a space in the template.

If you change the name attribute, CMS may not be able to map any existing content back to this editable tag.

All editables within a given module must have unique name attributes.
Name attributes are case sensitive and must only include letters, numbers, hyphens and underscores.

#### ** label= **

`label=` optional, recommended

We recommend also including a `label=` attribute. This provides a user friendly name for the editable tag, that is shown in the editor.

If there is no label attribute included in your code, CMS will use the name attribute.
You can include spaces and other characters in a label attribute.

#### ** hint= **

`hint=` optional

If you need, you can add additional help text for editors and marketers using the `hint=` attribute.

You can include spaces and other characters in a label attribute.
Try to keep hints short, to avoid adding clutter to the interface.


<!-- tabs:end -->


#### The `<module>` tag

All editable tags must be contained within a module tag. Module tags are used to group together editables in a way that makes sense for an editor, for example all of the navigation elements, or a block with an image, a headline and a CTA button.

``` html
<module name="module1" label="Module with a headline">
...
</module>
```

> `<module>` is an html tag and it has to be used semantically - otherwise CMS wouldn't know if an editable was inside it or not.
You can wrap a `<module>` tag around any html you like and not all of the html needs to be inside module tags.

> A module tag must not go inside another module tag.

> You can include multiple editable tags within a module tag.

> Modules also have `name=""`, `label=""` and `hint=""` as attributes.

> You can let editors manipulate how modules are displayed using `Modulezones`.

#### The `<modulezone>` tag

A modulezone is part of an email where the editor can add modules from a set defined in the template. Once modules are added they can be hidden or re-ordered.

In the template HTML a `<modulezone>` tag is used to create a modulezone. Like an `<editable>` or a `<module>` tag, a `<modulezone>` tag must have a `name=` attribute, `label=` is recommended and `hint=` can be used if necessary.

Inside the `<modulezone>` tag a collection of modules is built using `<module>` tags.

``` html
<modulezone name="maincontent" label="Main Content Area">
 <module name="heromodule" label="Hero Image with text">
 ...
 </module>
 <module name="oneproduct" label="One Product Module">
 ...
 </module>
 <module name="twoproduct" label="Two Product Module">
 ...
 </module>
</modulezone>
```

> All modulezones in a template must have a unique name attribute.

> All modules within a modulezone must have a unique name attribute (but you can have two modules with the same name, as long as they're in separate modulezones)

> The first child tag within a `<modulezone>` should always be a `<module>` tag. Any HTML within a `<modulezone>` tag that isn't wrapped in a `<module>` tag will be removed.

> `<modulezone>` and `<module>` tags should be either before or after table structure tags, not inside them.
>
>For example:
>
>```html
><table><tr><td><modulezone><module><table><tr><td>
>```
>instead of
>```html
>...</tr><modulezone><module><tr><td>
>```

> The label attribute from a `<module>` (or name attribute if there is no label) is used in the dropdown menu for adding modules in the modulezone editor.

> When an editor starts a new mailing, the modulezone is always empty.

##### Considerations when building with `<modulezone>`

A template can be built as one big modulezone, but this often provides a bad user experience. Often it's better to have a modulezone for header modules at the top of the email, then a series of content modules in a main modulezone. By taking this approach you can ensure that the design of the email isn't compromised by ill-advised module choices by a user.

You can still use `<module>` tags outside a modulezone. Those modules will be fixed and can't be removed or re-ordered by the editor.
