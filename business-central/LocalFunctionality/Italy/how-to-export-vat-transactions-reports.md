---
title: How to export VAT transactions reports [IT]
description: The following article explains how to export VAT Transactions Reports. After you create a report, you can release it, and then export it for the authorities.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 12/06/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Export VAT transactions reports in the Italian version
After you create a report, you can release it, and then export it for the authorities. To change the report, make sure that the Modify Submitted Reports check box is enabled in the VAT Report Setup page. If it isn't, to change the report when you want to correct an error, you have to create a new report, add the report with the error in the original report number, and then create a corrective report. For more information, see [Correct VAT Transactions Reports](how-to-correct-vat-transactions-reports.md).  

It's only possible to change the lines and fields when the document has the status Open. In the Released status, only the receipt no. is available for change. In the Submitted status, all fields are locked.  

## To export and submit a VAT transaction report  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Reports**, and then choose the related link.  
2.  Select an existing report or create a new report:  

    - Select the relevant VAT report from the list, and then choose the **Edit** action.  
    - Choose the **New** action, and create a new report. For more information, see [Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md).  

3.  Review the transaction details. To exclude a line from being reported to the tax authority, on the line, clear the **Incl. in Report** check box. To see the VAT entries that the line is based on, choose the drill-down button in the **Amount** field.

    > [!NOTE]  
    >  You can create an empty report, that is, a report that has no lines, in the case in which there are no transactions to report.  

4.  Choose the **Release** action. The **Status** field is updated to Released.  

    [!INCLUDE[prod_short](../../includes/prod_short.md)] validates that the VAT report is valid and ready for submission. If the validation fails, the errors are shown on the **VAT Report Error Log** page so that you can make the appropriate changes.  

    After you release a VAT report, you can't edit it. But, you can change the report by reopening it. Choose the **Reopen** action.  

5.  Choose the **Export** action. The **Export VAT Transactions** batch job opens.  
6.  Select the **Detailed Export** check box, depending on your needs. The field controls whether to export the data in detailed format or in aggregate. If aggregate, lines are further grouped by VAT registration number or fiscal code.  
7.  Choose the **OK** button.

    The VAT report is exported as a .ccf file. You can now submit the report to the tax authorities by using the tool from the Italian Revenue Agency. Use the guidelines provided by the authority. For more information, see the [Italian Revenue Agency](https://go.microsoft.com/fwlink/?LinkID=206524).  

    After you receive a response from the tax authorities, you must update the VAT report.  

8.  On the **General** FastTab, in the **Tax Auth. Receipt No.** field, specify the receipt number that you received from the tax authorities. In the **Tax Auth. Doc. No.** field, specify the document number that you receive.  
9. Choose the **Mark as Submitted** action to finalize the report. The **Status** field is updated to Submitted.  

    > [!NOTE]  
    >  You can modify a report that has the status of Submitted only if you have enabled the **Modify Submitted Reports** check box on the **VAT Report Setup** page.  

## Related information  
[Correct VAT Transactions Reports](how-to-correct-vat-transactions-reports.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
