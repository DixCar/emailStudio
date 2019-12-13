### Limit character for CTA

<!-- tabs:start -->

#### ** Basic **

Set max limit character for CTA

<video controls pause style="max-width: 50%; height: auto; margin: 10 0 auto;">
  <source src="http://currys-ssl.cdn.dixons.com/css/themes/email/LAB/EmailStudioGuide/v1/CTA_character_count.webm">
  Your browser does not support the video tag.
</video>

<i class="fas fa-fw fa-bug"></i> Only works if the text starts with a letter (if only numbers are used, the function will not work - see video above on full screen)



``` html
<field type="text" name="text" hint="14 character limit recommendation to keep the text on one line" default="CTA"></field>
<a replace="{% if text.size > 14 %}too much text{% else %}{{text}}{% endif %}">CTA</a>
```

where:

`field` is use to set default value

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

#### ** CSS **
N/A

<!-- tabs:end -->
