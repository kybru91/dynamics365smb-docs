---
title: Building Reports in Power BI Desktop to Display Business Central Data
description: Make your data available as a data source in Power BI and build powerful reports of the state of your business.
author: jswymer
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 10/23/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Building Power BI reports for displaying [!INCLUDE [prod_long](includes/prod_long.md)] data

You can make your [!INCLUDE[prod_long](includes/prod_long.md)] data available as a data source in Power BI Desktop and build powerful reports about the state of your business.

This article describes how to start using Power BI Desktop to create reports that display [!INCLUDE[prod_long](includes/prod_long.md)] data. After you create reports, you can publish them to your Power BI service or share them with all users in your organization. When the reports are in the Power BI service, users that are set up for it can view the reports in [!INCLUDE[prod_long](includes/prod_long.md)].

## Get ready

- Sign up for the Power BI service.

  If you aren't signed up, go to [https://powerbi.microsoft.com](https://powerbi.microsoft.com). When you sign up, use your work email address and password.

- Download [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

  Power BI Desktop is a free application you install on your local computer. Learn more at [Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

- Make sure the data you want in the report is available as an API page or published as a web service. Learn more in [Expose data through API pages or OData web services](admin-powerbi-setup.md#exposedata).

<!--- For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, get the following information:

  - The OData URL for [!INCLUDE[prod_short](includes/prod_short.md)].
  
    Typically, this URL has the format `http[s]://[computer]:[port]/[serverinstance]/ODataV4`, for example, `https://localhost:7048/BC190/ODataV4`. If you have a multi-tenant deployment, include the tenant in the URL, for example, `https://localhost:7048/BC190/ODataV4?tenant=tenant1`.
  - A user name and web service access key of a [!INCLUDE[prod_short](includes/prod_short.md)] account.

    To get data from [!INCLUDE[prod_short](includes/prod_short.md)], Power BI uses basic authentication. So, you'll need a user name and web service access key to connect. The account might be your own user account, or your organization may have specific account for this purpose.-->

- Download the [!INCLUDE [prod_short](includes/prod_short.md)] report theme (optional).

  Learn more in [Use the [!INCLUDE [prod_short](includes/prod_short.md)] report theme](#theme) in this article.

[!INCLUDE[note-multicompany-reports](includes/note-multicompany-reports.md)]

## <a name="getdata"></a>Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop

The first task in creating reports is to add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop. Once connected, you can start to build the report.

1. Start Power BI Desktop.
2. Select **Get Data**.

    If you don't see **Get Data**, select the **File** menu, then **Get Data**.
3. On the **Get Data** page, select **Online Services**.
4. In the **Online Services** pane, do one of the following steps:

    - To connect to [!INCLUDE [prod_short](includes/prod_short.md)] online, select **Dynamics 365 Business Central**, then **Connect**.
    <!--- To connect to  [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, select **Dynamics 365 Business Central (on-premises)**, then **Connect**.-->

5. Sign-in to [!INCLUDE [prod_short](includes/prod_short.md)] (one-time only).

    If you aren't signed in to [!INCLUDE [prod_short](includes/prod_short.md)] from Power BI desktop, you're prompted to sign in.

    - For [!INCLUDE [prod_short](includes/prod_short.md)] online, select **Sign in**, and then choose the relevant account. Use the same account that you use to sign into [!INCLUDE [prod_short](includes/prod_short.md)]. When done, select **Connect**.

    <!--- For [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, first enter the OData URL for [!INCLUDE[prod_short](includes/prod_short.md)], then select **OK**. When prompted, enter the user name and password of the account to use for connecting to [!INCLUDE[prod_short](includes/prod_short.md)]. In the **Password** box, enter the web service access key. When done, select **Connect**.-->

    > [!NOTE]  
    > After you connect to [!INCLUDE[prod_short](includes/prod_short.md)], you won't be prompted again to sign in. [How do I change or clear the account I'm currently using to connect to Business Central from Power BI Desktop?](/dynamics365/business-central/power-bi-faq?tabs=designer#perms)

6. When connected, Power BI contacts the [!INCLUDE [prod_short](includes/prod_short.md)] service. The **Navigator** window displays the data sources that are available for building reports. Select a folder to expand it and show the available data sources.

   These data sources represent all web services and API pages that are published for [!INCLUDE [prod_short](includes/prod_short.md)], grouped by environments and companies. With [!INCLUDE [prod_short](includes/prod_short.md)] online, **Navigator** has the following structure:

    - **Environment name**
      - **Company name**
        - **Advanced APIs**

          This folder lists advanced API pages published by Microsoft, like the [Business Central automation APIs](/dynamics365/business-central/dev-itpro/administration/itpro-introduction-to-automation-apis) and [custom API pages for Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-develop-custom-api). Custom API pages are further grouped in folders according to the [APIPublisher](/dynamics365/business-central/dev-itpro/developer/properties/devenv-apipublisher-property)/[APIGroup](/dynamics365/business-central/dev-itpro/developer/properties/devenv-apigroup-property) properties of the API page source code.

        - **Standard APIs v2.0**

          This folder lists the API pages exposed by the [Business Central API V2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/).

        - **Web services \(legacy)**

          This folder lists pages, codeunits, and queries that are published as web services in Business Central.

    <!--
    > [!NOTE]
    > The structure for Business Central on-premises is different because it doesn't support API pages.-->

7. Select the data source or sources that you want to add to your data model, and then select the **Load** button.
8. If later you want to add more Business Central data, you can repeat the previous steps.

Once the data is loaded, you can see it in the right navigation on the page. At this point, you're connected to your [!INCLUDE[prod_short](includes/prod_short.md)] data, and you can begin building your Power BI report.  

> [!TIP]
> For more information about using Power BI Desktop, see [Get started with Power BI Desktop](/power-bi/fundamentals/desktop-getting-started).

## Creating accessible reports

It's important to make your reports usable for as many people as possible. Try to design reports so that they don't require any special adaptation to meet specific needs of different users. Make sure the design lets users take advantage of standard assistive technologies, like screen readers. Power BI includes various accessibility features, tools, and guidelines to help you achieve this goal. For more information, [Design Power BI reports for accessibility](/power-bi/create-reports/desktop-accessibility-creating-reports) in the Power BI documentation.

## Creating reports to display data associated with a list

You can create reports that display in a FactBox of a [!INCLUDE [prod_short](includes/prod_short.md)] list page. The reports can contain data about the record selected in the list. Creating these reports is similar to other reports, except there are a few things to do to make sure the reports display as expected. Learn more in [Creating Power BI Reports for Displaying List Data in [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-powerbi-reports-factbox.md).

## <a name="theme"></a>Using the [!INCLUDE [prod_short](includes/prod_short.md)] report theme (optional)

Before building your report, we recommend that you download and import the [!INCLUDE [prod_short](includes/prod_short.md)] theme file. The theme file creates a color palette so you can build reports with the same color styling as the [!INCLUDE [prod_short](includes/prod_short.md)] apps, without requiring you to define custom colors for each visual.

> [!NOTE]
> This task is optional. You can always create your reports, and then download and apply the style template later.

### Download the theme

The theme file is available as a json file on Microsoft Power BI Community Themes Gallery. To download the theme file, do the following steps:

1. Go to [Microsoft Power BI Community Themes Gallery for Microsoft Dynamics 365 Business Central](https://community.powerbi.com/t5/Themes-Gallery/Microsoft-Dynamics-365-Business-Central/m-p/385875).
2. Select the download attachment **Microsoft Dynamics Business Central.json**.

### Import the theme on a report

After you download the [!INCLUDE [prod_short](includes/prod_short.md)] report theme, you can import it to your reports. To import the theme, Select the **View** > **Themes** > **Browse for themes**. Learn more at [Power BI Desktop - Import custom report themes](/power-bi/create-reports/desktop-report-themes#import-custom-report-theme-files).

## Publish reports

After you create or modify a report, you can publish the report to your Power BI service and also share it with others in your organization. After you publish a report, it's available in Power BI. The report also becomes available for selection in [!INCLUDE[prod_short](includes/prod_short.md)].

To publish a report, select **Publish** on the **Home** tab of the ribbon or from the **File** menu. If you're signed into Power BI service, the report is published to this service. Otherwise, you're prompted to sign in. 

## Distribute or share a report

There are a couple ways to get reports to your coworkers and others:

- Distribute reports as .pbix files.

    Reports are stored on your computer as .pbix files. You can distribute the report .pbix file to users, like any other file. Then, users can upload the file to their Power BI Service. See [Upload reports from files](across-working-with-powerbi.md#upload).

    > [!NOTE]
    > Distributing reports in this manner means that refreshing data for reports is done individually by each user. This situation might impact [!INCLUDE[prod_short](includes/prod_short.md)] performance.

- Share report from your Power BI service

    If you have a Power BI Pro license, you can share the report with others, directly from your Power BI service. Learn more at [Power BI - Share a dashboard or report](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

## How to develop cross-company or cross-environment Power BI reports

The [!INCLUDE[prod_short](includes/prod_short.md)] API endpoints all have the prefix `https://api.businesscentral.dynamics.com/v2.0/<environment_name>/api/v2.0` followed by `/companies({company_id})/accounts({id})` (here we use the `accounts` API as an illustration). You can use this structure to create PowerQuery queries that load data for multiple companies or multiple environments if the user who is reading data can access them.

To set up a query to load data for multiple companies, follow these steps:

1. Take the PowerQuery query that loads data for a single company. Convert it to a custom Power Query function that takes the company ID (or maybe the environment name) as parameters. To learn more, go to [Using custom Power Query functions](/power-query/custom-function).
1. Now use the new custom function in a PowerQuery query, where you map the function over a list of companies and then merge the datasets using the [Table.Combine](/powerquery-m/table-combine) Power Query function.

## <a name="advancedopts"></a>Advanced: Customize language, timeout, database replica, or page size for your Business Central data source

The Power BI connector for [!INCLUDE [prod_short](includes/prod_short.md)] supports several advanced properties for connecting to a Business Central data source that you can set in your Power Query queries. The following table describes the parameters.

|Parameter|Description|Default|Learn more at|
|-|-|-|-|
|AcceptLanguage|This parameter allows you to specify preferred languages for responses, ensuring users receive messages and translatable strings in their desired language. It sets the language in which the Business Central API session runs. It influences the language of error messages, formatted values in AL, and other values that depend on language or culture.<br><br>Setting this parameter improves user satisfaction and makes the data more accessible and relevant.|*not specified*|[Use locale values in multiple-language Power BI reports](/power-bi/guidance/multiple-language-locale#load-a-report-in-power-bi).|
|ODataMaxPageSize|This parameter limits the number of entities per results page, which allows for more flexibility when connecting to large datasets or using complex queries. It sets the maximum number of records to return for each page when calling an API. For example, if your table **Customers** has 13,000 records and ODataMaxPageSize is set to 5000, Power BI makes 3 API calls to get your customers. The first call gets 5,000 records, the next one gets 5000 more, and the last call gets the remaining 3000. This option can't be higher than the maximum page size enforced by Business Central, which is 20000.<br><br>Setting this parameter ensures efficient and responsive data retrieval, leading to faster insights and decision-making. You can't exceed the maximum page size defined on the service.|5000|[ODataPreferenceHeader.MaxPageSize Property](/dotnet/api/microsoft.odata.odatapreferenceheader.maxpagesize)|
|Timeout|This parameter defines the maximum duration for a request before cancellation. It sets the timeout for each single API call to Business Central. Its value can't exceed the timeout enforced on the Business Central service, which is currentæy 10 minutes (00:10:00).<br><br>Setting this parameter helps manage system resources effectively and prevents long-running queries from impacting overall system performance. Users experience minimal delays and interruptions, ensuring a smoother workflow. |00:08:00|[OData.Feed](/powerquery-m/odata-feed)|
|UseReadOnlyReplica|This parameter determines whether requests target the primary database or a read-only replica. Offloading read operations from the primary database can significantly boost performance.<br><br> Setting this property leads to faster data retrieval and improved system stability, especially during peak usage times.|true||

### Configure the advanced parameters

1. Start Power BI Desktop.
2. Complete the step that suits your scenario:

   # [Edit existing report](#tab/existing)

   1. Select **File** > **Open**.
   1. Browse for and select the report (.pbix). 
   1. In the ribbon, select **Transform Data** to open the **Power Query Editor**.

   # [Create new report](#tab/new)

   1. In the ribbon, select **Get Data**. If you don't see **Get Data**, select the **File** menu, then **Get Data**.
   1. On the **Get Data** page, select **Online Services** > **Dynamics 365 Business Central** > **Connect**.
   1. In the **Navigator** window, select the API endpoint that you want to load data from.
   1. Select **Transform Data** instead of **Load** as you might normally do. This step opens **Power Query Editor**.

   ---

3. In **Power Query Editor**, select **Advanced Editor** from the ribbon.
4. In **Advanced Editor**, locate the line that starts with `Source =`:

   ```powerquery
   Source = Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, null),
   ```

5. In the line, replace the fourth parameter of `Dynamics365BusinessCentral.ApiContentsWithOptions` with a comma separated list of properties and values you want to set, for example:

   ```powerquery
   Source = Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, [UseReadOnlyReplica = true, Timeout = Duration.From("00:07:00"), ODataMaxPageSize = 10000, AcceptLanguage = "it-it"])
   ```

6. Select **Done** to close **Advanced Editor**.
7. Select **Close & Apply** to save the changes and close Power Query Editor.

## Fixing problems

### "Expression.Error: The environment 'Production' does not exist." error when specifying a Business Central environment

> **APPLIES TO:** Business Central online

When you connect to Business Central online from Power BI, or when you install a Power BI app from Microsoft AppSource that uses Business Central data, you might be prompted to input the Business Central environment you want to connect to.

If you get an error similar to "Expression.Error: The environment 'Production' does not exist.", follow these steps to troubleshoot:

1. Make sure you're using the right credentials to access Business Central. These credentials might not be the same credentials you use to access Power BI. [How do I change or clear the account I'm currently using to connect to Business Central from Power BI Desktop?](/dynamics365/business-central/power-bi-faq?tabs=designer#perms)
2. If your environment is an embed ISV environment, you need to specify the embed ISV name in parenthesis as part of the environment name. For example, if you want to connect to an environment named Production from the embed ISV named Fabrikam, you have to specify "PRODUCTION (fabrikam)" as environment name.

### "Can't insert a record. Current connection intent is Read-Only." error connecting to custom API page

> **APPLIES TO:** Business Central online

By default, reports that use Business Central data connect to a read-only replica of the Business Central database. In rare cases, depending on the page design, you might get an error when you try to connect to and get data from the page. The error looks like this:

`Dynamics365BusinessCentral: Request failed: The remote server returned an error: (400) Bad Request. (Can't insert a record. Current connection intent is Read-Only. CorrelationId: [...])".`

If you're using a custom API page, we recommend you rework the page to make sure it doesn't make database modifications when it's just reading data. But in case your scenario requires it, you can [configure the connector to use a read-write connection instead](#advancedopts).

## Related information

[Enabling Your Business Data for Power BI](admin-powerbi-setup.md)  
[Business Intelligence](bi.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finance](finance.md)  
[Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
