<!--
<i class="fas fa-fw fa-exclamation"></i> IMPORTANT
<i class="fas fa-fw fa-bug"></i> BUG
<i class="fas fa-fw fa-wrench"></i> IMPROVEMENT
<i class="fas fa-fw fa-broom"></i> MAINTENANCE
-->

## CPCW Personalisation Fields

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

<i class="fas fa-fw fa-broom"></i> Note: both `CPCW` and `CPCWB` are using same `psb` for OPT-OUT link



#### ** CPCW-PRICE-PROMISE **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_4_name">CPCW-PRICE-PROMISE</esp-personalization>
```

Will export as HTML:

``` html
<a class="ios" href="https://www.currys.co.uk/gbuk/price-promise-1023-theme.html?<%@ include view='dixCPCW_CMS_TRC' %>" _label="TsCs_HOM" style="font-family: Arial, Helvetica, sans-serif; font-size:11px; line-height: 13px; color:#333332; text-decoration:underline; -webkit-text-size-adjust: 90%;">currys.co.uk</a>.
```



#### ** CPCW-PRIVACY-POLICY **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_5_name">CPCW-PRIVACY-POLICY</esp-personalization>
```

Will export as HTML:

``` html
<a class="ios" href="https://www.currys.co.uk/gbuk/privacy-on-currys-321-commercial.html?<%@ include view='dixCPCW_CMS_TRC' %>" _label="TsCs" style="text-decoration:underline; color:#333333;">Privacy&nbsp;Policy</a>.
```



#### ** CPCW-CUSTOMER_SERVICE **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_6_name">CPCW-CUSTOMER_SERVICE</esp-personalization>
```

Will export as HTML:

``` html
<a class="ios" style="text-decoration:underline; color:#333333; font-size:11px;" href="mailto:customer.services@currys.co.uk">customer.services@currys.co.uk</a>
```


<!-- tabs:end -->



## Personalisation Fields

The footer backed in links relay on Personalisation Fields created in CMS.

<i class="fas fa-fw fa-exclamation"></i> Is important to not delete any of personalisation field as this can impact internal name of them assigned by CMS

<!-- tabs:start -->

#### ** CPCWB-OPT-OUT **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_3_name">CPCWB-OPT-OUT</esp-personalization>
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

<i class="fas fa-fw fa-broom"></i> Note: both `CPCW` and `CPCWB` are using same `psb` for OPT-OUT link



#### ** CPCWB-PRICE-PROMISE **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_9_name">CPCWB-PRICE-PROMISE</esp-personalization>
```

Will export as HTML:

``` html
<a class="ios" href="https://business.currys.co.uk/customer-services/price-promise.jtp?from=main-menu?<%@ include view='dixDIXtrackingPCWB' %>&utm_content=TsCs_PricePromise" _label="TsCs_PricePromise" style="text-decoration:underline; color:#333333; font-size:11px;">www.business.currys.co.uk</a>.
```



#### ** CPCWB-PRIVACY-POLICY **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_8_name">CPCWB-PRIVACY-POLICY</esp-personalization>
```

Will export as HTML:

``` html
<a class="ios" href="https://www.pcworldbusiness.co.uk/legal/privacy.jtp?from=main-menu?<%@ include view='dixDIXtrackingPCWB' %>&utm_content=TsCs_PrivacyPolicy" _label="TsCs_PrivacyPolicy" style="text-decoration:underline; color:#333333; font-size:11px;">Privacy&nbsp;Policy</a>.
```



#### ** CPCWB-CUSTOMER_SERVICE **

HTML code for CMS template:

``` html
<esp-personalization field="personalization_field_6_name">CPCWB-CUSTOMER_SERVICE</esp-personalization>
```

Will export as HTML:

``` html
<a class="ios" style="text-decoration:underline; color:#333333; font-size:11px;" href="mailto:pcwb_customerservices@dixonscarphone.com">pcwb_customerservices@dixonscarphone.com</a>.
```


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

<i class="fas fa-fw fa-broom"></i> Tracking Link can be turned OFF in each module or globally from document settings to use *CMS Tracking Link Management* instead.



#### ** CPCWB TRACKING LINK **

Adobe Campaign Personalisation Block `dixDIXtrackingPCWB`:

``` js
<%@ include view='dixDIXtrackingPCWB' %>
```

Will export as HTML below with prefix `?` for **Standard** Links `[ST]` or `&` for **Movable Ink** links `&`:

``` html
utm_campaign=<%= CampaignName %>&utm_medium=email&utm_source=PCWB_wk<%= targetData.WeekNo %>&utm_term=<%= message.delivery.id %>
```

<i class="fas fa-fw fa-broom"></i> Tracking Link can be turned OFF in each module or globally from document settings to use *CMS Tracking Link Management* instead.

<!-- tabs:end -->
