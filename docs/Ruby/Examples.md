## RICH TEXT EDITOR WYSIWYG

### Text Align

<!-- tabs:start -->

#### ** Basic **

Left, Center, Right

![alt text](//currys-ssl.cdn.dixons.com/css/themes/email/LAB/EmailStudioGuide/v1/WYSWIG_text_align.PNG "")

Set default align value and turn on the WYSIWYG widget:
``` html
align="center" replace-align="{{editables.headline.align}}"
```
where:

`editables` and `align` turned on the widget

`headline` identifying name/label on `<editable>` tag
```html
<editable name="headline" label="headline">
```
Simple example:
```html
<td align="center" replace-align="{{editables.headline.align}}">
  <editable name="headline" label="headline">
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
        </table>
      </td>
    </tr>
  </table>
</module>
```

<!-- tabs:end -->


### Text Styling

<!-- tabs:start -->

#### ** Basic **

Subscript, Superscript, Bold, Italic, Smart Item (personalisation link)

![alt text](//currys-ssl.cdn.dixons.com/css/themes/email/LAB/EmailStudioGuide/v1/WYSWIG_rich_text.PNG "")

Turn on the WYSIWYG widget and options:
``` html
type="rich" allow-styles="subscript superscript bold italic link personalisation
```
where:

`type="rich"` turned on the widget

`allow-styles="subscript superscript bold italic link personalisation"` set available options

Simple example:
```html
<field type="rich" allow-styles="subscript superscript bold italic link personalisation" name="content" label="Headline text"></field>
<content replace="{{content}}">THE DEALS ARE TOO GOOD TO MISS</content>
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

<!-- tabs:end -->

### Limit character for CTA

<!-- tabs:start -->

#### ** Basic **

Set max limit character for CTA

<video controls pause style="max-width:100%; min-width:50%; height: auto; margin: 10 0 auto;">
  <source src="http://currys-ssl.cdn.dixons.com/css/themes/email/LAB/EmailStudioGuide/v1/CTA_character_count.webm">
  Your browser does not support the video tag.
</video>

<i class="fas fa-fw fa-bug"></i> Only works if the text starts with a letter (if only numbers are used, the function will not work - see video above on full screen)

``` html
<field type="text" name="text" hint="14 character limit recommendation to keep the text on one line" default="CTA"></field>
<a replace="{% if text.size > 14 %}too much text{% else %}{{text}}{% endif %}">CTA</a>
```

where:

`default="CTA"` default text value

`replace="{% if text.size > 14 %}too much text{% else %}{{text}}{% endif %}"` will change text on CTA if hit more than 14 characters


#### ** HTML **
Example of module
```html
<module name="CB04" label="CB04 - CTA">
  <field type="text" name="padTop" label="Outer Padding - Top (just number)" default="10"></field>
  <field type="text" name="padBottom" label="Outer Padding - Bottom (just number)" default="10"></field>
  <table role="presentation" width="100%" align="center" cellspacing="0" cellpadding="0" border="0">
    <tr>
      <td>
        <table role="presentation" width="650" align="center" cellspacing="0" cellpadding="0" border="0" class="fw">
          <tr>
            <td style="padding: 10px 0px 10px 0px;" replace-style="padding:{{padTop}}px 0px {{padBottom}}px 0px;">
              <table role="presentation" width="100%" class="container" border="0" cellpadding="0" cellspacing="0" align="center">
                <tr>
                  <td align="center" class="x-60">
                    <!-- $$ 1x CTA ¬ set: link, tracking, bgcolort -->
                    <table role="presentation" width="190" class="noBG" border="0" cellpadding="0" cellspacing="0" align="center">
                      <tr>
                        <td height="40" valign="middle" align="center" bgcolor="#00224f;" replace-bgcolor="{{editables.cta.ctacol}}" class="noBG hA">
                          <editable name="cta" label="CTA">
                            <field type="text" name="text" hint="14 character limit recommendation to keep the text on one line" default="CTA"></field>
                            <field type="color" allow-custom="true" name="ctacol" label="CTA background colour" default="#00224f" hint="Select CTA background colour by clicking on the colour picker or pasting a HEX code with the hashtag"> </field>
                            <field type="color" name="ctaTXTcol" label="CTA text colour" default="#ffffff"></field>
                            <field type="number" name="ctasize" label="CTA text size" default="18"></field>
                            <field type="href" name="href" label="Link URL" default="https://www.carphonewarehouse.com/"></field>
                            <a href="https://www.carphonewarehouse.com/" replace-href="{{href}}" replace="{% if text.size > 14 %}too much text{% else %}{{text}}{% endif %}" style="background-color:#00224f; border-radius:3px; color:#ffffff; display:block; font-family:Arial, Helvetica, sans-serif; font-weight: bold; font-size:18px; line-height:40px; text-align:center; text-decoration:none; -webkit-text-size-adjust:inherit;" replace-style="background-color:{{ctacol}}; border-radius:3px; color:{{ctaTXTcol}}; display:block; font-family:Arial, Helvetica, sans-serif; font-weight: bold; font-size:{{ctasize}}px;line-height:40px; text-align:center; text-decoration:none; -webkit-text-size-adjust:inherit;">CTA</a> </editable>
                        </td>
                      </tr>
                    </table>
                  </td>
                </tr>
              </table>
            </td>
          </tr>
        </table>
      </td>
    </tr>
  </table>
</module>
```

<!-- tabs:end -->

### Background and Text Colours (#HEX)

<!-- tabs:start -->

#### ** Basic **

Allowing to change Background Colour and Text Colour by #HEX or Colour Picker

![ColourHEX](https://user-images.githubusercontent.com/32497506/70802338-21162780-1da9-11ea-9031-469a642cad7e.PNG)


``` html
<td bgcolor="#00224f;" replace-bgcolor="{{editables.cta.ctacol}}">
  <field type="color" allow-custom="true" name="ctacol" label="CTA background colour" default="#00224f" hint="Select CTA background colour by clicking on the colour picker or pasting a HEX code with the hashtag"> </field>
  <field type="color" name="ctaTXTcol" label="CTA text colour" default="#ffffff"></field>
  <a style="background-color:#00224f;" replace-style="background-color:{{ctacol}}; color:{{ctaTXTcol}};">CTA</a>

```

where:

`bgcolor="#00224f;"` and `default="#00224f"` and `style="background-color:#00224f;"` default values

`replace-bgcolor="{{editables.cta.ctacol}}"` and `replace-style="background-color:{{ctacol}}; color:{{ctaTXTcol}};"` variables

`allow-custom="true"` turn on the widget

`name="ctacol"` and `name="ctaTXTcol"` pointers

#### ** HTML **
Example of module
```html
<module name="CB04" label="CB04 - CTA">
  <field type="text" name="padTop" label="Outer Padding - Top (just number)" default="10"></field>
  <field type="text" name="padBottom" label="Outer Padding - Bottom (just number)" default="10"></field>
  <table role="presentation" width="100%" align="center" cellspacing="0" cellpadding="0" border="0">
    <tr>
      <td>
        <table role="presentation" width="650" align="center" cellspacing="0" cellpadding="0" border="0" class="fw">
          <tr>
            <td style="padding: 10px 0px 10px 0px;" replace-style="padding:{{padTop}}px 0px {{padBottom}}px 0px;">
              <table role="presentation" width="100%" class="container" border="0" cellpadding="0" cellspacing="0" align="center">
                <tr>
                  <td align="center" class="x-60">
                    <!-- $$ 1x CTA ¬ set: link, tracking, bgcolort -->
                    <table role="presentation" width="190" class="noBG" border="0" cellpadding="0" cellspacing="0" align="center">
                      <tr>
                        <td height="40" valign="middle" align="center" bgcolor="#00224f;" replace-bgcolor="{{editables.cta.ctacol}}" class="noBG hA">
                          <editable name="cta" label="CTA">
                            <field type="text" name="text" hint="14 character limit recommendation to keep the text on one line" default="CTA"></field>
                            <field type="color" allow-custom="true" name="ctacol" label="CTA background colour" default="#00224f" hint="Select CTA background colour by clicking on the colour picker or pasting a HEX code with the hashtag"> </field>
                            <field type="color" name="ctaTXTcol" label="CTA text colour" default="#ffffff"></field>
                            <field type="number" name="ctasize" label="CTA text size" default="18"></field>
                            <field type="href" name="href" label="Link URL" default="https://www.carphonewarehouse.com/"></field>
                            <a href="https://www.carphonewarehouse.com/" replace-href="{{href}}" replace="{% if text.size > 14 %}too much text{% else %}{{text}}{% endif %}" style="background-color:#00224f; border-radius:3px; color:#ffffff; display:block; font-family:Arial, Helvetica, sans-serif; font-weight: bold; font-size:18px; line-height:40px; text-align:center; text-decoration:none; -webkit-text-size-adjust:inherit;" replace-style="background-color:{{ctacol}}; border-radius:3px; color:{{ctaTXTcol}}; display:block; font-family:Arial, Helvetica, sans-serif; font-weight: bold; font-size:{{ctasize}}px;line-height:40px; text-align:center; text-decoration:none; -webkit-text-size-adjust:inherit;">CTA</a> </editable>
                        </td>
                      </tr>
                    </table>
                  </td>
                </tr>
              </table>
            </td>
          </tr>
        </table>
      </td>
    </tr>
  </table>
</module>
```

<!-- tabs:end -->

### Padding

<!-- tabs:start -->

#### ** Basic **

Allowing to change Padding value

![Padding](https://user-images.githubusercontent.com/32497506/70806467-4dcf3c80-1db3-11ea-9f17-bb2ab6a6f613.PNG)


``` html
<field type="number" name="padTop" label="Outer Padding - Top (just number)" default="20"></field>
<field type="number" name="padBottom" label="Outer Padding - Bottom (just number)" default="20"></field>
<field type="number" name="padTop1" label="Inner Padding - Top (just number)" default="10"></field>
<field type="number" name="padBottom1" label="Inner Padding - Bottom (just number)" default="10"></field>
...
<td style="padding: 20px 0px 20px 0px;" replace-style="padding:{{padTop}}px 0px {{padBottom}}px 0px;">
...
<th style="padding: 10px 0px 10px 0px;" replace-style="padding:{{padTop1}}px 0px {{padBottom1}}px 0px;">
```

where:

`default="20` and `default="10"` and `style="padding: 20px 0px 20px 0px;"` and `style="padding: 10px 0px 10px 0px;"` default values

`replace-style="padding:{{padTop}}px 0px {{padBottom}}px 0px;"` and `replace-style="padding:{{padTop1}}px 0px {{padBottom1}}px 0px;"` variables

`name="padTop"` and `name="padBottom"` and `name="padTop1"` and `name="padBottom1"` pointers

#### ** HTML **
Example of module
```html
<module name="CB08_2" label="CB08.2 - Offer Pod 1 (Full width image)">
  <field type="dropdown" name="lr" label="Image Left or Right" default="ltr">
    <choice label="Left" value="ltr"/>
    <choice label="Right" value="rtl"/>
  </field>
  <field type="color" allow-custom="true" name="bgcol" label="Background colour" default="#FFFFFF" hint="Need a custom colour, click on a colour swatch in the dropdown menu">
    <choice label="Blue" value="#f0f8fa"/>
    <choice label="White" value="#ffffff"/>
  </field>
  <field type="number" name="padTop" label="Outer Padding - Top (just number)" default="20"></field>
  <field type="number" name="padBottom" label="Outer Padding - Bottom (just number)" default="20"></field>
  <field type="number" name="padTop1" label="Inner Padding - Top (just number)" default="10"></field>
  <field type="number" name="padBottom1" label="Inner Padding - Bottom (just number)" default="10"></field>
  <field type="href" name="href" label="Link URL" default="https://www.carphonewarehouse.com/"></field>
  <!-- $ 1NOM -->
  <table role="presentation" width="100%" align="center" cellspacing="0" cellpadding="0" border="0">
    <tr>
      <td style="padding: 20px 0px 20px 0px;" replace-style="padding:{{padTop}}px 0px {{padBottom}}px 0px;">
        <table role="presentation" width="650" class="fw" border="0" cellpadding="0" cellspacing="0" align="center" style="border:0;" bgcolor="#FFFFFF" replace-bgcolor="{{bgcol}}">
          <tbody>
            <tr>
              <!-- set: direction [image and text can be oposite (left/right)] -->
              <th align="center" width="650" style="padding: 10px 0px 10px 0px;" replace-style="padding:{{padTop1}}px 0px {{padBottom1}}px 0px;" class="fw dB hA" dir="ltr" replace-dir="{{lr}}">
                <table role="presentation" width="100%" class="fw" border="0" cellspacing="0" cellpadding="0">
                  <tr>
                    <!-- COLUMN LEFT ¬ IMAGE ¬ set: bgcolor -->
                    <th class="fw dB">
                      <table role="presentation" width="325" border="0" cellspacing="0" cellpadding="0" class="fw" dir="ltr">
                        <!-- $$ IMAGE -->
                        <tr>
                          <td>
                            <editable name="image" label="Image">
                              <field type="src" name="src" label="Image"></field>
                              <field type="text" name="alt" label="Alt text" default=" "></field>
                              <a href="https://www.carphonewarehouse.com/" replace-href="{{module.href}}" rule="{% remove_outer_unless module.href %}"><img align="center" width="100%" class="fw hA" src="http://images.emlcdn.net/cdn/1002135/ce45d2d2-0390-4e6b-b92c-b479768f301a/f6f43cf807bf429096bccdcd3ceb8d2b.jpg" replace-src="{{src}}" alt="" replace-alt="{{alt}}" border="0" style="width:100%; max-width:100%; display:block; border:0px;" /></a> </editable>
                          </td>
                        </tr>
                      </table>
                    </th>
                    <th width="25" height="25" class="dB" align="center" valign="top">&nbsp;</th>
                    <!-- COLUMN RIGHT ¬ TEXT -->
                    <th width="300" class="fw dB" style="font-weight:normal;">
                      <table role="presentation" width="100%" border="0" align="center" cellpadding="0" cellspacing="0" dir="ltr">
                        <!-- $ HEADER ¬ set: color, text-transform -->
                        <tr rule="{% remove_unless editables.heading.content%}">
                          <td style="padding: 0px 0px 10px 0px;">
                            <table role="presentation" width="100%" border="0" cellpadding="0" cellspacing="0" align="center">
                              <tr>
                                <td align="center" valign="middle" style="text-align: center;padding: 0 10px 0 10px;" replace-style="text-align:{{editables.heading.align}};padding: 0 {{modules.formatting.paddinglr}}px 0 {{modules.formatting.paddinglr}}px;">
                                  <editable name="heading" label="Headline text">
                                    <field type="rich" allow-styles="subscript superscript bold italic link personalisation" name="content" label="Headline text"></field>
                                    <field type="align" name="align" label="Text align" default="center"/>
                                    <field type="color" name="color" label="Headline colour" default="#00224f"></field>
                                    <field type="number" name="textsize" label="Text Size" default="16"></field>
                                    <p style="font-family:Arial, Helvetica, sans-serif; font-size:16px; line-height:19px;color:#00224f;text-transform:none; margin: 0" replace-style="font-family:Arial, Helvetica, sans-serif; font-size:{{textsize}}px; line-height:1.2; color:{{color}};text-transform:none; margin: 0" replace="{{content}}"><strong>Tech prizes to be won!</strong></p>
                                  </editable>
                                </td>
                              </tr>
                            </table>
                          </td>
                        </tr>
                        <!-- $ COPY ¬ set: text, text-align, color -->
                        <tr rule="{% remove_unless editables.txt.content%}">
                          <td>
                            <table role="presentation" width="100%" border="0" cellpadding="0" cellspacing="0" align="center">
                              <tr>
                                <td align="center" valign="middle" style="font-family: Arial, Helvetica, sans-serif; font-size:14px; line-height:17px; mso-line-height-rule:exactly;color:#5a5b5c;padding: 0 10px 0 10px;" replace-style="font-family:Arial, Helvetica, sans-serif; font-size:{{editables.txt.textsize}}px; line-height:1.2; mso-line-height-rule:exactly; color:{{editables.txt.color}}; text-align:{{editables.txt.align}};padding: 0 {{modules.formatting.paddinglr}}px 0 {{modules.formatting.paddinglr}}px;">
                                  <editable name="txt" label="Body text">
                                    <field type="rich" allow-styles="subscript superscript bold italic link personalisation" name="content"></field>
                                    <field type="align" name="align" label="Text align" default="center"/>
                                    <field type="color" name="color" label="Body text colour" default="#5a5b5c"></field>
                                    <field type="number" name="textsize" label="Body text size" default="16"></field>
                                    <content replace="{{content}}">For the chance to bag yourself some amazing tech prizes, enter our monthly prize draw now.</content>
                                  </editable>
                                </td>
                              </tr>
                            </table>
                          </td>
                        </tr>
                        <!-- $ CTA ¬ set: bgcolor, background-color, color, lenght, link, tracking -->
                        <tr>
                          <td style="padding: 20px 0px 0px 0px;" align="center" replace-align="{{editables.cta.align}}">
                            <table role="presentation" width="190" class="noBG" border="0" cellpadding="0" cellspacing="0" align="center" replace-align="{{editables.cta.align}}">
                              <tr>
                                <td height="40" valign="middle" align="center" bgcolor="#00224f" replace-bgcolor="{{editables.cta.ctacol}}" class="noBG hA">
                                  <editable name="cta" label="CTA">
                                    <field type="text" name="text" hint="14 character limit recommendation to keep the text on one line" default="CTA"></field>
                                    <field type="align" name="align" label="Text align" default="center"/>
                                    <field type="color" allow-custom="true" name="ctacol" label="CTA background colour" default="#00224f" hint="Select CTA background colour by clicking on the colour picker or pasting a HEX code with the hashtag"> </field>
                                    <field type="color" name="ctaTXTcol" label="CTA text colour" default="#ffffff"></field>
                                    <field type="number" name="ctasize" label="CTA text size" default="18"></field>
                                    <field type="href" name="href" label="Link URL" default="https://www.carphonewarehouse.com/"></field>
                                    <a href="https://www.carphonewarehouse.com/" replace-href="{{href}}" replace="{% if text.size > 14 %}too much text{% else %}{{text}}{% endif %}" style="background-color:#00224f; border-radius:3px; color:#ffffff; display:block; font-family:Arial, Helvetica, sans-serif; font-weight: bold; font-size:18px; line-height:40px; text-align:center; text-decoration:none; -webkit-text-size-adjust:inherit;" replace-style="background-color:{{ctacol}}; border-radius:3px; color:{{ctaTXTcol}}; display:block; font-family:Arial, Helvetica, sans-serif; font-weight: bold; font-size:{{ctasize}}px;line-height:40px; text-align:center; text-decoration:none; -webkit-text-size-adjust:inherit;">Shop now</a></editable>
                                </td>
                              </tr>
                            </table>
                          </td>
                        </tr>
                      </table>
                    </th>
                  </tr>
                </table>
              </th>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
  </table>
</module>
```

<!-- tabs:end -->

## DROPDOWN MENU

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


### Background Colour choice

<!-- tabs:start -->

#### ** Basic **

Dropdown menu for Background Colours

![ColourChoice](https://user-images.githubusercontent.com/32497506/70804092-810ecd00-1dad-11ea-8e0f-21dd3a287ec7.PNG)


``` html
<field type="color" allow-custom="true" name="bgcol" label="Background colour" default="#FFFFFF" hint="Need a custom colour, click on a colour swatch in the dropdown menu">
  <choice label="Blue" value="#f0f8fa"/>
  <choice label="White" value="#ffffff"/>
</field>
<table bgcolor="#FFFFFF" replace-bgcolor="{{bgcol}}">
```

where:

`default="#FFFFFF"` and `bgcolor="#FFFFFF"` default values

`replace-bgcolor="{{bgcol}}"` variables

`allow-custom="true"` turn on the widget

`name="bgcol"` pointer

`<choice label="Blue" value="#f0f8fa"/>` and `<choice label="White" value="#ffffff"/>` available choices

#### ** HTML **
Example of module
```html
<module name="CB08_2" label="CB08.2 - Offer Pod 1 (Full width image)">
  <field type="dropdown" name="lr" label="Image Left or Right" default="ltr">
    <choice label="Left" value="ltr"/>
    <choice label="Right" value="rtl"/>
  </field>
  <field type="color" allow-custom="true" name="bgcol" label="Background colour" default="#FFFFFF" hint="Need a custom colour, click on a colour swatch in the dropdown menu">
    <choice label="Blue" value="#f0f8fa"/>
    <choice label="White" value="#ffffff"/>
  </field>
  <field type="number" name="padTop" label="Outer Padding - Top (just number)" default="20"></field>
  <field type="number" name="padBottom" label="Outer Padding - Bottom (just number)" default="20"></field>
  <field type="number" name="padTop1" label="Inner Padding - Top (just number)" default="10"></field>
  <field type="number" name="padBottom1" label="Inner Padding - Bottom (just number)" default="10"></field>
  <field type="href" name="href" label="Link URL" default="https://www.carphonewarehouse.com/"></field>
  <!-- $ 1NOM -->
  <table role="presentation" width="100%" align="center" cellspacing="0" cellpadding="0" border="0">
    <tr>
      <td style="padding: 20px 0px 20px 0px;" replace-style="padding:{{padTop}}px 0px {{padBottom}}px 0px;">
        <table role="presentation" width="650" class="fw" border="0" cellpadding="0" cellspacing="0" align="center" style="border:0;" bgcolor="#FFFFFF" replace-bgcolor="{{bgcol}}">
          <tbody>
            <tr>
              <!-- set: direction [image and text can be oposite (left/right)] -->
              <th align="center" width="650" style="padding: 10px 0px 10px 0px;" replace-style="padding:{{padTop1}}px 0px {{padBottom1}}px 0px;" class="fw dB hA" dir="ltr" replace-dir="{{lr}}">
                <table role="presentation" width="100%" class="fw" border="0" cellspacing="0" cellpadding="0">
                  <tr>
                    <!-- COLUMN LEFT ¬ IMAGE ¬ set: bgcolor -->
                    <th class="fw dB">
                      <table role="presentation" width="325" border="0" cellspacing="0" cellpadding="0" class="fw" dir="ltr">
                        <!-- $$ IMAGE -->
                        <tr>
                          <td>
                            <editable name="image" label="Image">
                              <field type="src" name="src" label="Image"></field>
                              <field type="text" name="alt" label="Alt text" default=" "></field>
                              <a href="https://www.carphonewarehouse.com/" replace-href="{{module.href}}" rule="{% remove_outer_unless module.href %}"><img align="center" width="100%" class="fw hA" src="http://images.emlcdn.net/cdn/1002135/ce45d2d2-0390-4e6b-b92c-b479768f301a/f6f43cf807bf429096bccdcd3ceb8d2b.jpg" replace-src="{{src}}" alt="" replace-alt="{{alt}}" border="0" style="width:100%; max-width:100%; display:block; border:0px;" /></a> </editable>
                          </td>
                        </tr>
                      </table>
                    </th>
                    <th width="25" height="25" class="dB" align="center" valign="top">&nbsp;</th>
                    <!-- COLUMN RIGHT ¬ TEXT -->
                    <th width="300" class="fw dB" style="font-weight:normal;">
                      <table role="presentation" width="100%" border="0" align="center" cellpadding="0" cellspacing="0" dir="ltr">
                        <!-- $ HEADER ¬ set: color, text-transform -->
                        <tr rule="{% remove_unless editables.heading.content%}">
                          <td style="padding: 0px 0px 10px 0px;">
                            <table role="presentation" width="100%" border="0" cellpadding="0" cellspacing="0" align="center">
                              <tr>
                                <td align="center" valign="middle" style="text-align: center;padding: 0 10px 0 10px;" replace-style="text-align:{{editables.heading.align}};padding: 0 {{modules.formatting.paddinglr}}px 0 {{modules.formatting.paddinglr}}px;">
                                  <editable name="heading" label="Headline text">
                                    <field type="rich" allow-styles="subscript superscript bold italic link personalisation" name="content" label="Headline text"></field>
                                    <field type="align" name="align" label="Text align" default="center"/>
                                    <field type="color" name="color" label="Headline colour" default="#00224f"></field>
                                    <field type="number" name="textsize" label="Text Size" default="16"></field>
                                    <p style="font-family:Arial, Helvetica, sans-serif; font-size:16px; line-height:19px;color:#00224f;text-transform:none; margin: 0" replace-style="font-family:Arial, Helvetica, sans-serif; font-size:{{textsize}}px; line-height:1.2; color:{{color}};text-transform:none; margin: 0" replace="{{content}}"><strong>Tech prizes to be won!</strong></p>
                                  </editable>
                                </td>
                              </tr>
                            </table>
                          </td>
                        </tr>
                        <!-- $ COPY ¬ set: text, text-align, color -->
                        <tr rule="{% remove_unless editables.txt.content%}">
                          <td>
                            <table role="presentation" width="100%" border="0" cellpadding="0" cellspacing="0" align="center">
                              <tr>
                                <td align="center" valign="middle" style="font-family: Arial, Helvetica, sans-serif; font-size:14px; line-height:17px; mso-line-height-rule:exactly;color:#5a5b5c;padding: 0 10px 0 10px;" replace-style="font-family:Arial, Helvetica, sans-serif; font-size:{{editables.txt.textsize}}px; line-height:1.2; mso-line-height-rule:exactly; color:{{editables.txt.color}}; text-align:{{editables.txt.align}};padding: 0 {{modules.formatting.paddinglr}}px 0 {{modules.formatting.paddinglr}}px;">
                                  <editable name="txt" label="Body text">
                                    <field type="rich" allow-styles="subscript superscript bold italic link personalisation" name="content"></field>
                                    <field type="align" name="align" label="Text align" default="center"/>
                                    <field type="color" name="color" label="Body text colour" default="#5a5b5c"></field>
                                    <field type="number" name="textsize" label="Body text size" default="16"></field>
                                    <content replace="{{content}}">For the chance to bag yourself some amazing tech prizes, enter our monthly prize draw now.</content>
                                  </editable>
                                </td>
                              </tr>
                            </table>
                          </td>
                        </tr>
                        <!-- $ CTA ¬ set: bgcolor, background-color, color, lenght, link, tracking -->
                        <tr>
                          <td style="padding: 20px 0px 0px 0px;" align="center" replace-align="{{editables.cta.align}}">
                            <table role="presentation" width="190" class="noBG" border="0" cellpadding="0" cellspacing="0" align="center" replace-align="{{editables.cta.align}}">
                              <tr>
                                <td height="40" valign="middle" align="center" bgcolor="#00224f" replace-bgcolor="{{editables.cta.ctacol}}" class="noBG hA">
                                  <editable name="cta" label="CTA">
                                    <field type="text" name="text" hint="14 character limit recommendation to keep the text on one line" default="CTA"></field>
                                    <field type="align" name="align" label="Text align" default="center"/>
                                    <field type="color" allow-custom="true" name="ctacol" label="CTA background colour" default="#00224f" hint="Select CTA background colour by clicking on the colour picker or pasting a HEX code with the hashtag"> </field>
                                    <field type="color" name="ctaTXTcol" label="CTA text colour" default="#ffffff"></field>
                                    <field type="number" name="ctasize" label="CTA text size" default="18"></field>
                                    <field type="href" name="href" label="Link URL" default="https://www.carphonewarehouse.com/"></field>
                                    <a href="https://www.carphonewarehouse.com/" replace-href="{{href}}" replace="{% if text.size > 14 %}too much text{% else %}{{text}}{% endif %}" style="background-color:#00224f; border-radius:3px; color:#ffffff; display:block; font-family:Arial, Helvetica, sans-serif; font-weight: bold; font-size:18px; line-height:40px; text-align:center; text-decoration:none; -webkit-text-size-adjust:inherit;" replace-style="background-color:{{ctacol}}; border-radius:3px; color:{{ctaTXTcol}}; display:block; font-family:Arial, Helvetica, sans-serif; font-weight: bold; font-size:{{ctasize}}px;line-height:40px; text-align:center; text-decoration:none; -webkit-text-size-adjust:inherit;">Shop now</a></editable>
                                </td>
                              </tr>
                            </table>
                          </td>
                        </tr>
                      </table>
                    </th>
                  </tr>
                </table>
              </th>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
  </table>
</module>
```

<!-- tabs:end -->
