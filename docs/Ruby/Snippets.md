<!--
<i class="fas fa-fw fa-exclamation"></i> IMPORTANT
<i class="fas fa-fw fa-bug"></i> BUG
<i class="fas fa-fw fa-wrench"></i> IMPROVEMENT
<i class="fas fa-fw fa-broom"></i> MAINTENANCE
-->

## Special Characters

Snippets allow us to use none friendly special characters in editable text


<!-- tabs:start -->

#### ** Snippet setup **

`|replace:` is looking for the string `'~TEXT~'` in text editor and replace it with `'ENCODED-HTML'`

<i class="fas fa-fw fa-exclamation"></i> Require `default="Default Value Text"` in `<field>` tag


``` html
<field type="rich" allow-styles="bold italic link superscript" name="content" default="Default Value Text"></field>

<content replace="{{ content|replace: '~NBSP~', '&nbsp;'|replace: '~NBH~', '&#8209;'|replace: '~GT~', '&gt;' }}"></content>"
```

<i class="fas fa-fw fa-wrench"></i> Is possible to support more characters by adding another `|replace: '~TEXT~', 'ENCODED-HTML'`


#### ** Supported Characters **

All supported list of characters

| EFFECT | WRITE AS | AUTO-CONVERTED | COMMENTS |
|:-:|:-:|:-:|:-|
| &nbsp;    | `~NBSP~`    | `&nbsp;` | non-breaking space |
| &#8209;   | `~NBH~`     | `&#8209;` | non-breaking hyphen |
| &gt;   | `~GT~`     | `&gt;` | greater-than sign (chevron) |


#### ** Depreciated Characters **

<i class="fas fa-fw fa-broom"></i> Depreciated list of characters. Seams to be fine to use below characters in way of a copy-and-paste as CMS supports UTF-8 characters

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


<!--

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

-->



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
