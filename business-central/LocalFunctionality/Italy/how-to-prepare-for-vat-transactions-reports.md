---
title: Prepare for VAT transactions reports [IT]
description: The following article explains how to prepare and submit the periodic VAT Transactions Reports to the tax authorities. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 11/17/2023
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Prepare for VAT transactions reports in the Italian version
You must submit periodic reports to the tax authorities to list all transactions that include VAT. The tax authority establishes the thresholds at which reporting is required. Currently, the threshold is set at zero, meaning that all transactions are to be reported. To prepare for these reports, you must set up VAT posting to include VAT transaction report amounts.  

## To set up VAT transaction amounts  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.  
2.  Choose the **VAT Transaction Report Amount** action.  
3.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**Individual Person**|Select if this customer is an individual person.|  
    |**Resident**|Specify if the customer is a resident in Italy.<br /><br /> If a customer isn't a resident, you must also specify a tax representative on the **Foreign Trade** FastTab.|  
    |**First Name**|Specifies the first name of the person.|  
    |**Last Name**|Specifies the last name of the person.|  
    |**Date of Birth**|Specifies the date of birth of the person.|  
    |**Place of Birth**|Specifies the place of birth of the person.|  

3.  If the customer isn't resident in Italy and isn't an individual person, you must specify a tax representative for the customer.  

    > [!NOTE]  
    >  Before you can specify a tax representative, you must have created the tax representative as a contact.  

### To specify a tax representative for a non-resident customer  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2. Select a customer.
2.  On the **Foreign Trade** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Tax Representative Type**|Specifies if the tax representative is a customer or a contact. You must set this field to **Contact**.|  
    |**Tax Representative No.**|Specify the contact that is the tax representative for this customer.|  

    You set up information, so that [!INCLUDE[prod_short](../../includes/prod_short.md)] tracks new transactions with VAT that meet the thresholds specified by the tax authorities. Before you create the first VAT transaction report, you should prepare the existing data. For more information, see [Update VAT Transactions Data](how-to-update-vat-transactions-data.md). You can then create VAT transactions reports. For more information, see [Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md).

## Related information  
 [Update VAT Transactions Data](how-to-update-vat-transactions-data.md)   
 [Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md)   
 [Italian VAT](italian-vat.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
