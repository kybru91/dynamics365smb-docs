---
title: Accelerated Depreciation [FR]
description: Learn how to use the accelerated depreciation method to post the extra tax amounts if they meet specified criteria in the French version.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: accelerated depreciation method, depreciation, extra tax amounts, tax depreciation, accounting depreciation, French version
ms.search.form: 5610, 5611, 5612
ms.date: 04/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Accelerated depreciation in the French version

Accelerated depreciation is calculated based on the differences between the accounting depreciation book and the tax depreciation book fixed asset, during the life of the fixed asset.

Fixed assets that have higher tax depreciation and lower accounting depreciation are depreciated using the accelerated depreciation method, as allowed by the tax authorities.  

Companies must use the accelerated depreciation method to post the extra tax amounts if they meet at least two of the following criteria:  

- They have more than 50 employees.  
- They have at least two million euros in assets.  
- They have at least four million euros in sales.  

## Depreciation book

The accelerated depreciation method helps you to calculate and post differences between tax depreciation amounts and accounting depreciation amounts that are allowed for fixed assets. To calculate accelerated depreciation for fixed assets, the following depreciation books must be set up:  

- The accounting depreciation book (integrated with the general ledger).  
- The tax depreciation book (not integrated with the general ledger).  

You must set up the tax book as a derogatory book by using an accelerated depreciation setup parameter. If this parameter is set, differences between the tax book and the accounting book are calculated and posted as accelerated depreciation amounts. Learn more in [Set Up Accelerated Depreciation](how-to-set-up-accelerated-depreciation.md).  

### Example

If you have a fixed asset valued at 1,000 euros that is depreciated in the accounting depreciation book over five years, and depreciated in the tax depreciation book over three years, then the accounting depreciation for the first year is 200 euros (1,000/5) and the tax depreciation for the first year is 333.33 euros (1,000/3). The accelerated depreciation amount is the difference between these two amounts: 133.33 euros (333.33 - 200).  

## Accelerated depreciation accounts

Accelerated depreciation uses the derogatory fixed asset posting type. Statistics and reports use this posting type to report the accelerated depreciation calculation. Learn more in [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md).  

There are two accounts to set up for derogatory amounts:  

- Positive accelerated depreciation amounts (increase of accelerated depreciation):  

  - Derogatory account  
  - Derogatory expense account  
  - Negative accelerated depreciation amounts (decrease of accelerated depreciation):  
  - Derogatory Acc. on Disposal  
  - Derog. Bal. Acc. on Disposal  

If you post an acquisition, depreciation, or disposal for the accounting depreciation book, the transaction is automatically duplicated and posted in the tax depreciation book when the journal is posted.  

After you set up the tax depreciation book and the accounting depreciation book, the accelerated depreciation is calculated automatically for fixed assets using the calculate depreciation batch job in the accounting depreciation book. Learn more in [Calculate Accelerated Depreciation](how-to-calculate-accelerated-depreciation.md).  

## Related information

- [Set Up Accelerated Depreciation](how-to-set-up-accelerated-depreciation.md)   
- [Calculate Accelerated Depreciation](how-to-calculate-accelerated-depreciation.md)   
- [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)   
- [Fixed Assets](../../fa-manage.md)  
- [France Local Functionality](france-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
