## Special Characters

`{{content|replace: 'ABC', 'XYZ'}}` making possible to use special characters in rich-text editor

<!-- tabs:start -->

#### ** Snippet setup **

Use `|replace:` function to find **any** string that contained `'~TEXT~'`, and replace it all with `'ENCODED-HTML'`


``` html
<content replace="{{content|replace: '~NBSP~', '&nbsp;'|replace: '~SUP1~', '&sup1;'|replace: '~SUP2~', '&sup2;'|replace: '~SUP3~', '&sup3;'|replace: '~DAGGER1~', '&dagger;'|replace: '~DAGGER2~', '&Dagger;'|replace: '~DEG~', '&deg;'|replace: '~CIRC~', '&circ;'|replace: '~AMP~', '&amp;'|replace: '~COPY~', '&copy;'|replace: '~REG~', '&reg;'|replace: '~TRADE~', '&trade;'|replace: '~NBH~', '&#8209;'|replace: '~£~', '&pound;'|replace: '~LSQUO~', '&lsquo;'|replace: '~RSQUO~', '&rsquo;'|replace: '~BULL~', '&bull;'|replace: '~HELLIP~', '&hellip;'|replace: '~RARR~', '&rarr;'}}">Lorem ipsum</content>"
```

#### ** List of Characters **

| EFFECT | WRITE AS | AUTO-CONVERTED | COMMENTS |
|:-:|:-:|:-:|:-|
| &nbsp;    | `~NBSP~`    | `&nbsp;` | non-breaking space |
| &sup1;    | `~SUP1~`    | `&sup1;` | if you need 4,5,6... use supercript with numbers instead |
| &sup2;    | `~SUP2~`    | `&sup2;` | if you need 4,5,6... use supercript with numbers instead |
| &sup3;    | `~SUP3~`    | `&sup3;` | if you need 4,5,6... use supercript with numbers instead |
| &dagger;  | `~DAGGER1~` | `&dagger;` | single-dagger |
| &Dagger;  | `~DAGGER2~` | `&Dagger;` | double-dagger |
| &circ;    | `~CIRC~`    | `&circ;` | modifier letter circumflex accent |
| &deg;     | `~DEG~`     | `&deg;` | degree sign |
| &amp;     | `~AMP~`     | `&amp;` | ampersand sign|
| &reg;     | `~REG~`     | `&reg;` | registered sign |
| &copy;    | `~COPY~`    | `&copy;` | copyright sign |
| &trade;   | `~TRADE~`   | `&trade;` | trademark sign |
| &#8209;   | `~NBH~`     | `&#8209;` | non-breaking hyphen `\u{2011}` |
| &pound;   | `~£~`       | `&pound;` | pound sign knowing as `&pound;` |
| &lsquo;   | `~LSQUO~`   | `&lsquo;` | left single quotation mark |
| &rsquo;   | `~RSQUO~`   | `&rsquo;` | right single quotation mark |
| &bull;    | `~BULL~`    | `&bull;` | bullet point |
| &hellip;  | `~HELLIP~`  | `&hellip;` | horizontal ellipsis |
| &rarr;    | `~RARR~`    | `&rarr;` | rightwards arrow |

<!-- tabs:end -->


## Module Padding

Use this snippet to add editable `padding-top` and `padding-bottom` within module (parent level)

<!-- tabs:start -->

#### ** Snippet setup **

Use `<fields>` to define editable fields for module and add `style` and `replace-style` to tag where padding is apply - in this case is `<td>`

``` html
<field type="number" name="moduleTopPad" label="Set the 'padding-top' value" hint="Use numbers only (default = 25)" default="25"></field>
<field type="number" name="moduleBottomPad" label="Set the 'padding-bottom' value" hint="Use numbers only (default = 25)" default="25"></field>
...
<td class="modPAD" style="padding-top:25px; padding-bottom:25px;" replace-style="padding-top:{{moduleTopPad}}px; padding-bottom:{{moduleBottomPad}}px;">
```


<!-- tabs:end -->
