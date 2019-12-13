### Uppercase

<!-- tabs:start -->

#### ** Basic **

Dropdown menu to choices for uppercase

![Uppercase](https://user-images.githubusercontent.com/32497506/70807557-adc6e280-1db5-11ea-89a1-9221d69b9a1f.PNG)


``` html
<td style="text-transform: uppercase" replace-style="text-transform: {{editables.headline.uppercase}}">
...
<field type="dropdown" name="uppercase" label="Headline all uppercase?" default="uppercase">
  <choice label="Yes" value="uppercase"/>
  <choice label="No" value="none"/>
</field>
```

where:

`style="text-transform: uppercase"` and `default="uppercase"` default values

`replace-style="text-transform: {{editables.headline.uppercase}}"` variables

`type="dropdown"` turn on the dropdown widget

`<choice label="Yes" value="uppercase"/>` and `<choice label="No" value="none"/>` available options (the `value` will inject to the variable)

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
