<!--
<i class="fas fa-fw fa-exclamation"></i> IMPORTANT
<i class="fas fa-fw fa-bug"></i> BUG
<i class="fas fa-fw fa-wrench"></i> IMPROVEMENT
<i class="fas fa-fw fa-broom"></i> MAINTENANCE
-->

## Personalisation Fields

The footer backed in links relay on Personalisation Fields created in CMS.

<i class="fas fa-fw fa-exclamation"></i> Is important to not delete any of personalisation field as this can impact internal name of them assigned by CMS

<!-- tabs:start -->

#### ** CPCW-OPT-OUT **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_3_name">CPCW-OPT-OUT</esp-personalization>
```

Will export as HTML:

``` js
<%@ include view='dixCoreFooterLinkOptOutCPCW' %>
```

Adobe Campaign Personalisation Block `dixCoreFooterLinkOptOutCPCW`:

``` html
<%
	var key = "0ABFBA777380F43B"
	var iv = "0000000000000000"
	var padding = "PKCS5PADDING"
	var method = "ECB"
	var id = chainProfile.partyId
	var id2 = chainProfile.pk_vm_brand
	var id3 = chainProfile.dk_vf_party_dims_assoc
	var cryptpId = escapeUrl(encryptDES(key, id, method, iv, padding))
	var cryptpBrand = escapeUrl(encryptDES(key, id2, method, iv, padding))
	var cryptpPartyAssoc = escapeUrl(encryptDES(key, id3, method, iv, padding))
%>
<a style="TEXT-DECORATION: underline;" href="<%@ value object='provider' xpath='@webAppURL' %>/webApp/dixDixonsPreference?pId=<%= cryptpId %>&brand=<%= cryptpBrand %>&partyAssoc=<%= cryptpPartyAssoc %>" _label="Preference Management">opt-out&nbsp;here</a>.
```

<i class="fas fa-fw fa-broom"></i> Note that the code contains `.` **full stop** at the end of the link



#### ** CPCW-PRICE-PROMISE **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_4_name">CPCW-PRICE-PROMISE</esp-personalization>
```

Will export as HTML:

``` html
<a href="https://www.currys.co.uk/gbuk/price-promise-1023-theme.html?<%@ include view='dixCPCW_CMS_TRC' %>" _label="t&c_HOM" style="font-family: Arial, Helvetica, sans-serif; font-size:11px; line-height: 13px; color:#333332; text-decoration:underline; -webkit-text-size-adjust: 90%;">currys.co.uk</a>
```

<i class="fas fa-fw fa-broom"></i> Note that the code do not contains `.` **full stop** at the end of the link



#### ** CPCW-PRIVACY-POLICY-LINK **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_5_name">CPCW-PRIVACY-POLICY-LINK</esp-personalization>
```

Will export as HTML:

``` html
<a href="https://www.currys.co.uk/gbuk/privacy-on-currys-321-commercial.html?<%@ include view='dixCPCW_CMS_TRC' %>" _label="TsCs" style="text-decoration:underline; color:#333333;">Privacy&nbsp;Policy</a>
```

<i class="fas fa-fw fa-broom"></i> Note that the code do not contains `.` **full stop** at the end of the link


<!-- tabs:end -->





## Tracking Link

Tracking Links can be added manually or by *CMS Tracking Link Management* or using our own build to inject Tracking dependent on module or document settings.

<!-- tabs:start -->
#### ** CPCW TRACKING LINK **

Adobe Campaign Personalisation Block `dixCPCW_CMS_TRC`:

``` js
<%@ include view='dixCPCW_CMS_TRC' %>
```

Will export as HTML below with prefix `?` for **Standard** Links `[ST]` or `&` for **Movable Ink** links `&`:

``` html
srcid=8324&cmpid=em~<%= targetData.ChainGroup %>~<%= CampaignName %>~<%= shortDayOfWeek%>_<%= CampaignType %>~wk<%= targetData.WeekNo %>~<%= targetData.Gender %>~<%= formatDate(new Date(targetData.BroadcastDate), '%4Y%2M%2D') %>~UNK~CMS~CMS~CMS~<%= message.delivery.id %>&emid=<%= chainProfile.partyId %>&mi_u=<%= chainProfile.partyId %>
```

<i class="fas fa-fw fa-broom"></i> Tracking Link is build for CPCW template is independent and can be turned OFF to use *CMS Tracking Link Management* instead.

<!-- tabs:end -->
