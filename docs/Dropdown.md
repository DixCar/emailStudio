### Font-Size choice

<!-- tabs:start -->

#### ** Basic **

Add Dropdown menu to change font-size (based on predefined CSS classes)

![alt text](//currys-ssl.cdn.dixons.com/css/themes/email/LAB/EmailStudioGuide/v1/DROPDOWN_text_size.PNG "")

Set default align value and turn on the WYSIWYG widget:
``` html
class="fz40" replace-class="fz{{editables.headline.mTextsize}} style="font-size:70px;" replace-style="font-size:{{editables.headline.dTextsize}}px;
```

where:

`class="fz40"` class (mobile default value)

`style="font-size:70px;"` inline (desktop default value)

`replace-class="fz{{editables.headline.mTextsize}}` is used to change the class name for mobile

`replace-style="font-size:{{editables.headline.dTextsize}}px;` is used to change the class name for desktop

Simple example:
```html
<td class="fz40" replace-class="fz{{editables.headline.mTextsize}}" style="font-size:70px;" replace-style="font-size:{{editables.headline.dTextsize}}px;">
  <editable name="headline" label="headline">
    <field type="align" name="align" label="align" default="center"></field>
    <field type="dropdown" name="dTextsize" label="Headline text size in Desktop" default="70">
      <choice label="60" value="60"/>
      <choice label="80" value="80"/>
    </field>
    <field type="dropdown" name="mTextsize" label="Headline text size in Mobile" default="40">
      <choice label="30" value="30"/>
      <choice label="40" value="40"/>
    </field>
```

#### ** HTML **
Example of module
```html
<module name="CB02" label="CB02 - Header text">
  <field type="number" name="padTop" label="Outer Padding - Top" default="20"></field>
  <field type="number" name="padBottom" label="Outer Padding - Bottom" default="20"></field>
  <field type="number" name="contentW" label="Content width" default="570" hint="Adjust the width in here for the header region"></field>
  <table width="570" replace-width="{{contentW}}" border="0" cellpadding="0" cellspacing="0" role="presentation" class="container">
    <tr>
      <td align="center" style="padding: 20px 10px 20px 10px" replace-style="padding: {{padTop}}px {{modules.formatting.paddinglr}}px {{padBottom}}px {{modules.formatting.paddinglr}}px;">
        <table border="0" cellpadding="0" cellspacing="0" role="presentation">
          <tr>
            <td class="fz40" replace-class="fz{{editables.headline.mTextsize}}" align="center" replace-align="{{editables.headline.align}}" valign="middle" style="font-family:'Impact', Arial, sans-serif; font-size:70px; line-height:76px; mso-line-height-rule:exactly; font-weight:normal; color:#1c2849; text-transform: uppercase" replace-style="font-family: 'Impact', Arial, sans-serif; font-size:{{editables.headline.dTextsize}}px; line-height:1.13; mso-line-height-rule:exactly; font-weight:normal; color:{{editables.headline.color}};text-transform: {{editables.headline.uppercase}}">
              <editable name="headline" label="headline">
                <field type="align" name="align" label="align" default="center"></field>
                <field type="dropdown" name="dTextsize" label="Headline text size in Desktop" default="70">
                  <choice label="60" value="60"/>
                  <choice label="65" value="65"/>
                  <choice label="70" value="70"/>
                  <choice label="80" value="80"/>
                </field>
                <field type="dropdown" name="mTextsize" label="Headline text size in Mobile" default="40">
                  <choice label="30" value="30"/>
                  <choice label="32" value="32"/>
                  <choice label="35" value="35"/>
                  <choice label="40" value="40"/>
                </field>
                <field type="color" name="color" label="Headline text colour" default="#1c2849"></field>
                <field type="dropdown" name="uppercase" label="Headline all uppercase?" default="uppercase">
                  <choice label="Yes" value="uppercase"/>
                  <choice label="No" value="none"/>
                </field>
                <field type="rich" allow-styles="subscript superscript bold italic link personalisation" name="content" label="Headline text"></field>
                <content replace="{{content}}">THE DEALS ARE TOO GOOD TO MISS</content>
              </editable>
            </td>
          </tr>
          <tr>
            <td class="fz35" replace-class="fz{{editables.subHeadline.mTextsize}}" align="center" replace-align="{{editables.subHeadline.align}}" valign="middle" style="font-family:Arial, Helvetica, sans-serif; font-size:27px; line-height:38px; mso-line-height-rule:exactly; font-weight:bold; color:#058ca8;" replace-style="font-family: Arial, Helvetica, sans-serif; font-size:{{editables.subHeadline.dTextsize}}px; line-height:1.12; mso-line-height-rule:exactly; font-weight:bold; color:{{editables.subHeadline.color}};">
              <editable name="subHeadline" label="subHeadline">
                <field type="align" name="align" label="align" default="center"></field>
                <field type="dropdown" name="dTextsize" label="Sub headline text size in Desktop" default="27">
                  <choice label="20" value="20"/>
                  <choice label="22" value="22"/>
                  <choice label="27" value="27"/>
                  <choice label="35" value="35"/>
                </field>
                <field type="dropdown" name="mTextsize" label="Sub headline text size in Mobile" default="20">
                  <choice label="20" value="20"/>
                  <choice label="22" value="22"/>
                  <choice label="25" value="25"/>
                  <choice label="30" value="30"/>
                </field>
                <field type="color" name="color" label="Sub headline text colour" default="#058ca8"></field>
                <field type="rich" allow-styles="subscript superscript bold italic link personalisation" name="content" label="Headline text"></field>
                <content replace="{{content}}">Save up to &pound;200</content>
              </editable>
            </td>
          </tr>
        </table>
      </td>
    </tr>
  </table>
</module>
```

#### ** CSS **
```css
<style type="text/css">
  .fz9 { font-size: 9px!important; }
  .fz20 { font-size: 20px!important; }
  .fz22 { font-size: 22px!important; }
  .fz25 { font-size: 25px!important; }
  .fz30 { font-size: 30px!important; }
  .fz32 { font-size: 32px!important; }
  .fz35 { font-size: 35px!important; }
  .fz40 { font-size: 40px!important; }
  .fz75 { font-size: 75px!important; }
  .fz80 { font-size: 80px!important; }
  .fz90 { font-size: 90px!important; }
  .fz95 { font-size: 95px!important; }
</style>
```

<!-- tabs:end -->
