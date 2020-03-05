<!--
<i class="fas fa-fw fa-exclamation"></i> IMPORTANT
<i class="fas fa-fw fa-bug"></i> BUG
<i class="fas fa-fw fa-wrench"></i> IMPROVEMENT
<i class="fas fa-fw fa-broom"></i> MAINTENANCE
-->

## Special Characters

Snippets allow us to use none friendly special characters in editable text


<!-- tabs:start -->

#### ** SETUP **

`|replace:` is looking for the string `'~TEXT~'` in text editor and replace it with `'ENCODED-HTML'`

<i class="fas fa-fw fa-exclamation"></i> Require `default="Default Value Text"` in `<field>` tag other way content will be empty


``` html
<field type="rich" allow-styles="bold italic link superscript" name="content" default="Default Value Text"></field>

<content replace="{{ content|replace: '~NBSP~', '&nbsp;'|replace: '~NBH~', '&#8209;'|replace: '~GT~', '&gt;'|replace: '~BRH~', '<br class=&quot;h&quot; /> '|replace: '~BR~', '<br /> ' }}"></content>"
```

<i class="fas fa-fw fa-wrench"></i> Is possible to support more characters by adding `|replace: '~TEXT~', 'ENCODED-HTML'`


#### ** Supported Characters **

All supported list of characters

| EFFECT | WRITE AS | AUTO-CONVERTED | COMMENTS |
|:-:|:-:|:-:|:-|
| &nbsp;    | `~NBSP~`    | `&nbsp;` | non-breaking space |
| &#8209;   | `~NBH~`     | `&#8209;` | non-breaking hyphen |
| &gt;   | `~GT~`     | `&gt;` | greater-than sign (chevron) |
| &lt;br class="h" /&gt;   | `~BRH~`     | `<br class=&quot;h&quot; />` | adding line break and hide it on mobile view |
| &lt;br /&gt;  | `~BR~`     | `<br />` | adding line break |


#### ** Other Characters **

<i class="fas fa-fw fa-broom"></i> Seams to be fine to use below characters in way of a copy-and-paste as CMS supports UTF-8 characters

| COPY | COMMENTS |
|:-:|:-|
| &sup1;    | if needed more like 4,5,6... use superscript with numbers instead |
| &sup2;    | if needed more like 4,5,6... use superscript with numbers instead |
| &sup3;    | if needed more like 4,5,6... use superscript with numbers instead |
| &dagger;  | single-dagger |
| &Dagger;  | double-dagger |
| &circ;    | modifier letter circumflex accent |
| &deg;     | degree sign |
| &amp;     | ampersand sign|
| &reg;     | registered sign |
| &copy;    | copyright sign |
| &trade;   | trademark sign |
| &pound;   | pound sign |
| &euro;   | euro sign |
| &lsquo;   | left single quotation mark |
| &rsquo;   | right single quotation mark |
| &bull;    | bullet point |
| &hellip;  | horizontal ellipsis |
| &rarr;    | rightwards arrow |


<!-- tabs:end -->


## Module Padding

Use this snippet to add editable `padding-top` and `padding-bottom` within module (parent level)

<!-- tabs:start -->

#### ** SETUP **

Use `<fields>` to define editable fields for module and add `style` and `replace-style` to tag where padding is apply - in this case is `<td>`

``` html
<field type="number" name="moduleTopPad" label="Set the 'padding-top' value" hint="Use numbers only (default = 25)" default="25"></field>
<field type="number" name="moduleBottomPad" label="Set the 'padding-bottom' value" hint="Use numbers only (default = 25)" default="25"></field>
...
<td class="modPAD" style="padding-top:25px; padding-bottom:25px;" replace-style="padding-top:{{moduleTopPad}}px; padding-bottom:{{moduleBottomPad}}px;">
```

<!-- tabs:end -->
