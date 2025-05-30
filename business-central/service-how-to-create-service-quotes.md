---
title: How to Create Service Quotes
description: Learn how to use a service quote as a preliminary draft for a service order, and then convert the quote to a service order.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 06/23/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Create Service Quotes
You can think of service quotes as the basis for service orders. In fact, they are almost identical. They both contain information such as who the customer is, the type of order, the item that needs service, billing and shipping information, and information about the actual service work.
 
You can use a service quote as a preliminary draft for a service order, and then convert the quote to a service order.  
  
## To create a service quote  
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Quotes**, and then choose the related link.  
2. Create a new service quote.  
3. In the **No.** field, enter a number for the service quote. Alternatively, if you have set up a number series for service quotes on the **Service Mgt. Setup** page, you can select <kbd>Enter</kbd> to select the next available service quote number.  
4. In the **Customer No.**  field, select the relevant customer from the list.  

  > [!Note]  
  >  The customer fields are filled in automatically with information from the **Customer** card. If a **Customer** card does not exist for the customer, and you have set up a customer template, you can create the customer from the service quote. Fill in the relevant fields, and then choose the **Create Customer** action.  
  
5. Depending on the settings on the **Mandatory Fields** FastTab on the **Service Mgt. Setup** page, you may need to fill in the **Service Order Type** field and the **Salesperson Code** field.  
6. Fill in the service item lines.  
7. Register estimated costs on the service lines.  
  
## Related information  
[Create Service Orders](service-how-to-create-service-orders.md)  
[Work on Service tasks](service-how-to-work-on-service-tasks.md)  

 

[!INCLUDE[footer-include](includes/footer-banner.md)]
