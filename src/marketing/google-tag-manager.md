---
conditions: Default.EE-B2B
title: Google Tag Manager
---

Google Tag Manager helps you manage the many tags, or snippets of code, that are related to your marketing campaign events. Google Tag Manager gives you the ability to add tracking tags to your site to measure the audience, or to personalize, retarget, or conduct search engine marketing initiatives.

Google Tag Manager directly transfers data and events to Google Analytics, Enhanced Ecommerce and other third-party analytics solutions, to produce a clear picture of how well your site, products, and promotions are performing.

You should have a Google Analytics and Tag Manager account to continue this process. The following instructions walk you through the process of configuring your Google accounts, configuring your Magento store, and creating a tag.

{: .bs-callout .bs-callout-info}
If your business operates in areas that are governed by the [General Data Protection Regulation]({% link stores/compliance-gdpr.md %}), see: [Google Settings for GDPR]({% link stores/compliance-gdpr-google.md %}).

## Step 1. Configure Your Google Analytics Account

See Google's [Set up Site Search][7] for the basics you need to get started. Also see the Google guides for [Google Analytics][1] and [Google Tag Manager][2].

1. Sign in to your Google Analytics account.

1. To enable **Internal Site Search Tracking**, do the following:

    * Navigate to **Select View** > **View Settings**.

    * Turn **Site Search Tracking** On.

    * Set **Query** parameter to “q”.

    * When complete, **Save** the settings.

1. To enable display features, do the following:

    * Choose **Property Settings**.

    * Under Advertising Features, set **Enable Demographics and Interest Reports** to “On”.

    * **Save** the settings.

1. To enable Ecommerce Tracking, do the following:

    * Navigate to **Select View** > **Ecommerce Settings**.

    * Set **Enable Ecommerce** to “On”.

    * Set **Enable Enhanced Ecommerce Reporting** to “On”.

    * **Save** the settings.

1. Reload the page to verify that all the settings remain “On”.

    {: .bs-callout .bs-callout-info}
    If not all settings are “On,” repeat the previous steps, save, and reload the page. Repeat this process until all settings are set to “On”.

## Step 2. Configure Your Google Tag Manager Account

The following instructions show how to configure a new container with the basic settings. A sample [Composer][4] configuration (.json) file is used to simplify the process, importing to generate a tag in a new container. For this example, we recommend that you create a new container, rather than modify an existing container.

{: .bs-callout .bs-callout-info}
For additional information, see Google's [Container export and import][5]. These instructions walk-through importing a sample JSON to a new container.

1. Right-click this link: [GMT_M2_Config_json.txt][6]. Choose **Save link as** to download the sample text file. Then, do the following:

    * Open the file in an editor, and save as `GMT_M2_Config.json`.

    * Zip the file to produce an archive called `GMT_M2_Config.zip`.

        The zipped file will be uploaded directly to Google Tag Manager, and does not need to be copied to your server.

1. Navigate to **Admin** > **Container** > **Import Container**.

1. Tap **Choose container file** and select the json file.

1. Under **Choose workspace**, tap **New**. Enter a title and description, then tap **Save**.

1. Select one of the following actions to import the file:

    * The **Overwrite** option should be selected for the new container.
    * The **Merge** option should be selected is you are using an existing container.

1. Tap Preview to review the tags, triggers, and variables.

1. To edit the **Google Analytics ID** that is referenced in variables, do the following:

    * Navigate to **Variables** > **User-Defined Variables**.

    * Choose **Google Analytics**. Then, update the placeholder (UA-xxxxxx-x) with your own **GA ID**.

1. Follow Google’s instructions to add tags, triggers, and variables to the new container.

    If you have settings in another container that you want to use, they can be moved to the new container.

1. Tap **Confirm** when complete. Follow Google’s instructions to publish the new container.

## Step 3. Configure Your Store

1. Log in to the Admin of your Magento store.

1. On the Admin sidebar, tap **Stores**. Then under **Settings**, choose **Configuration**.

1. In the panel on the left under** Sales**, choose **Google API**.

1. Expand ![]({% link images/images/btn-expand.png %}) the **Google Analytics** section, and configure:

    ![]({% link images/images-ee/config-sales-google-api-google-analytics-google-tag-manager.png %}){: .zoom} 
    [*Google API - Google Tag Manager*]({% link configuration/sales/google-api.md -%})

    * Set **Enable** to “Yes".

    * Set **Account type** to “Google Tag Manager”.

    * In the **Container ID** field, enter your GTM ID. (GTM-xxxxxx)

    * If you are also using Google Analytics to content experiments, set **Enable Content Experiments** to “Yes”.

    * Use the default values for the remaining fields.

1. When complete, tap <span class="btn">Save Config</span>.

1. Test your Google Tag Manager settings to verify that everything works correctly.

## Field Descriptions

|Field|Scope|Description|
|--- |--- |--- |
|Enable|Store View|Determines if Google Analytics Enhanced Ecommerce can be used to analyze activity in your store.Options include: Yes / No|
|Account type|Store View|Determines the Google tracking code that is used to monitor store activity and traffic.  Options include:Google AnalyticsGoogle Tag Manager|
|Anonymize IP|Store View|Determines if identifying information is removed from IP addresses that appear in Google Analytics results.|
|Enable Content Experiments|Store View|Activates Google Content Experiments, which can be used to test up to ten different versions of the same page. Options: Yes / No|
|Container Id|Store View|If Google Tag manager is already installed and configured for your store, the Container ID appears automatically in this field.|
|List property for the catalog page|Store View|Identifies the Tag Manager property associated with the catalog page. Default value: Catalog Page|
|List property for the cross-sell block|Store View|Identifies the Tag Manager property associated with the cross-sell block. Default value:Cross-sell|
|List property for the up-sell block|Store View|Identifies the Tag Manager property associated with the up-sell block. Default value: Up-sell|
|List property for the related products block|Store View|Identifies the Tag Manager property associated with the related products block. Default value: Related Products|
|List property for the search results page|Store View|Identifies the Tag Manager property associated with the search results page. Default value: Search Results|
|“Internal Promotions” for promotions field “Label”|Store View|Identifies the Tag Manager property associated with the labels for internal promotions. Default value: Label|
{:style="table-layout:auto"}

[1]: https://support.google.com/analytics/answer/1008015?hl=en
[2]: https://support.google.com/tagmanager/answer/6102821?hl=en
[3]: https://support.google.com/analytics/answer/1012264?hl=en
[4]: http://devdocs.magento.com/guides/v2.3/extension-dev-guide/intro/intro-composer.html
[5]: https://support.google.com/tagmanager/answer/6106997?hl=en
[6]: https://docs.magento.com/m2/downloads/GTM_M2_Config_json.txt
[7]: https://support.google.com/analytics/answer/1012264?hl=en
