Use links below to download available latest `Frameworks` and `Modules` or grab `CodeSnippets` to use within your campaign.

p> Always use only latest version of available templates.

<!-- <i class="fas fa-fw fa-file-code"></i><i class="fas fa-fw fa-file-medical"></i><i class="fas fa-fw fa-th-list"></i><i class="fas fa-fw fa-file-alt"></i>  -->


## Frameworks


<!-- [filename](_includes/download-frames.md ':include') -->
- [<i class="fas fa-fw fa-file-download"></i>Currys](https://dixonsretail.sharepoint.com/sites/emailcrm/Shared%20Documents/_Assets/__Templates/Adobe%20Campaign/Master%20Template/AC_Skeleton_Currys.html?csf=1 'download')
- [<i class="fas fa-fw fa-file-download"></i>PCWorld](https://dixonsretail.sharepoint.com/sites/emailcrm/Shared%20Documents/_Assets/__Templates/Adobe%20Campaign/Master%20Template/AC_Skeleton_PCWorld.html?csf=1 'download')
- [<i class="fas fa-fw fa-file-download"></i>PCWBusiness](https://dixonsretail.sharepoint.com/sites/emailcrm/Shared%20Documents/_Assets/__Templates/Adobe%20Campaign/Master%20Template/AC_Skeleton_PCWBusiness.html?csf=1 'download')
- [<i class="fas fa-fw fa-times"></i>iD Mobile](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>TeamKnowHow](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>DixonsTravel](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>CarphoneWarehouse](# 'disabled')

##  Modules

<!-- [filename](_includes/download-modules.md ':include') -->
- [<i class="fas fa-fw fa-file-download"></i>CurrysPCWorld](https://dixonsretail.sharepoint.com/sites/emailcrm/Shared%20Documents/_Assets/__Templates/Adobe%20Campaign/Master%20Template/AC_Sections_CPCW.html?csf=1 'download')
- [<i class="fas fa-fw fa-file-download"></i>PCWBusiness](https://dixonsretail.sharepoint.com/sites/emailcrm/Shared%20Documents/_Assets/__Templates/Adobe%20Campaign/Master%20Template/AC_Sections_PCWBusiness.html?csf=1&e=6a3403629d8740949ef87c5ba6f963af 'download')
- [<i class="fas fa-fw fa-file-download"></i>VML](https://dixonsretail.sharepoint.com/sites/emailcrm/Shared%20Documents/_Assets/__Templates/Adobe%20Campaign/Master%20Template/AC_VML.html?csf=1&e=6a3403629d8740949ef87c5ba6f963af 'download')
<!-- - [<i class="fas fa-fw fa-times"></i>iD Mobile](# 'disabled') -->

p> We provided both `TH` and `Table Alignment` modules, however we highly recommended use only `TH` modules.

## CSS

- [<i class="fas fa-fw fa-times"></i>CSS: CPCW](# 'disabled')

c> From 2.5 version the embedded `CSS` was moved away from templates and linking as separate `CSS` to protect core templates functionality. However, on send time the _Adobe Campaign_ ESP will embedding `CSS` back.

If you have to use your ad-hoc `CSS` use additional `<style>` or removed from final version of email campaign:

``` HTML
<!-- ad-hoc stylesheet -->
<style type="text/css">
@media only screen and (min-width: 0px) and (max-width: 650px) {
}
@media only screen and (min-width: 441px) and (max-width: 650px) {
}
@media only screen and (max-width: 440px) {
}
</style>
```

##  Grid

<!-- [filename](_includes/download-grid.md ':include') -->
- [<i class="fas fa-fw fa-times"></i>Framework](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>mBNR](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>TEXT](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>1 COLUMN](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>2 COLUMN](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>3 COLUMN](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>4 COLUMN](# 'disabled')
- [<i class="fas fa-fw fa-times"></i>Snippets](# 'disabled')

i> **Grid** template is not yet available, however we are using it for `OLB 2.0`.


##  Plain Text Template

Use code below to provide generic `Plain Text` template to use with any of template within _Adobe Campaign_.

``` html
You've received the plain text version of our email. Click below to view online with images.
<%@ include view='MirrorPageUrl' %>

To unsubscribe, click here:
<%@ include view='dixDIXPrefManagement' %>
```

p> Above code is mandatory to use with any campaign within _AdobeCampaign_.
