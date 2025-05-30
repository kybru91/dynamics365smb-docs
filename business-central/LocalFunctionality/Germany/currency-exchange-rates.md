---
title: Currency Exchange Rates [DE]
description: At fiscal year-end, adjust currency exchange rates for payables and receivables to ensure accurate annual balance valuation.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: adjust exchange rates, currency exchange rates, valuation methods, German version, Germany
ms.date: 03/10/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Currency exchange rates in the German version

At the end of the fiscal year, you must adjust currency exchange rates for payables and receivables so that they're valued correctly in the annual balance. The **Adjust Exchange Rates** batch job supports different valuation methods in order to meet legal requirements in Germany.  

## Valuation methods

According to the Bilanz Modernisierungs Gesetz (BilMoG), payables and receivables are valued differently depending on the difference between the reference date and the due date. This is managed by the **Adjust Exchange Rates** batch job where you can specify which valuation method to use. If the due date is less than one year after the reference date, the **Adjust Exchange Rates** batch job must be run using the lowest value valuation method.  

The following table describes the valuation methods.  

|Valuation method|Description|  
|----------------------|---------------------------------------|  
|**BilMoG (Germany)**|Beginning in 2010, each ledger entry is adjusted as follows:<br><br/>- If the due date is less than one year after the reference date, payable/receivable transactions are valued at the actual exchange rate.<br><br/>- If the due date is more than one year after the reference date, payable/receivable transactions are valued at the lowest value, with the possibility of appreciation in value (Wertaufholung) up to the initial value. <br><br/>**Note:** Ledger entries must contain a due date. An entry that doesn't have a due date is treated as a long term liability.|  
|**Lowest value**|Exchange rates are adjusted by using the lowest value of the two exchange rates. Currency losses are always calculated and posted. Currency gains are only calculated and posted up to the original local currency value of the transaction.<br><br/> This ensures that receivables aren't valued above their original posting amounts, and that payables aren't valued below their original posting amounts.|  
|**Standard**|Exchange rates are adjusted according to standard valuation principles. Full unrealized gains and losses are calculated and posted. If the transaction is partially applied, only the remaining amount is included in the adjustment. Learn more in [Adjust Exchange Rates](#valuation-methods).|  

German companies must use the **BilMoG (Germany)** option when they run the **Adjust Exchange Rates** batch job. This ensures that each transaction is adjusted using the appropriate valuation method as required in Germany. This also enables two fields in the request page, where you can specify the two dates that must be used to calculate the adjustment. The following table describes the fields.  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Valuation Reference Date**|Specifies the base date that is used to calculate which entries are short-term entries.|  
|**Short term liabilities until**|Specifies the date that separates short-term entries from long-term entries. Short-term entries have a due date that is before or on this date. The default value is the value of the **Valuation Reference Date** field plus one year.|  

## Related information

- [Update Currency Exchange Rates](../../finance-how-update-currencies.md)  
- [Set Up an Additional Reporting Currency](../../finance-how-setup-additional-currencies.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
