---
title: Nets import format
description: This article provides information about importing payment information in the Nets format.
author: AdamTrukawka
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.technology: 
audience: Application User
ms.reviewer: johnmichalak
ms.search.region: Norway
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.search.form: BankCustPaymIdTable, CustEInvoiceIntegrationeInvoice, CustEInvoiceIntegrationTypePaymMode, CustEinvoiceIntegrationTypeTable, CustPaymMode, LedgerJournalTransCustPaym
---

# Nets import format

[!include [banner](../../includes/banner.md)]

This article provides information about importing payment information in the Nets format.

You can import enrollment messages, AvtaleGiro and eInvoice, together with payment messages, optical character recognition (OCR), AvtaleGiro, and eInvoice, in the Nets file format.

## Import a Nets bank file
To import the file provided by Nets bank, complete the following steps.

1. Go to the **Payment journal** page
2. Click **Lines.**
3. Click **Functions** &gt; **Import payments**.
4. In the dialog box, select the method of payment, and then browse to the location of the file to import. In the same dialog box, you must also specify a **Sender ID** to ensure that the correct file is selected for import (00008080 value should be specified on the dialog for the Nets bank). 
   > [!NOTE]
   > Before you can complete this step, you must have already imported the **Nets (No)** configurations from Lifecycle Services (LCS) and set up the Nets method of payment. For more information, see [File formats for methods of payments](../europe/emea-select-file-formats-for-the-method-of-payments.md).

The process is similar for importing enrollment messages from the **eInvoice enrollment and answer** page. Regardless of whether the file has only payment transactions, only enrollment messages, or both, everything will be imported in one action.

## OCR, AvtaleGiro, and eInvoice transactions import
OCR, Avtalegiro, and eInvoice transactions should be imported and settled based on the payment ID and generated while the invoices are posted. As a result, payment journal lines should be created and marked for settlement with corresponding invoices. **Note**: Transactions corresponding to the free text message codes are not settled after import. You must set up a 16-digit payment ID on the **Payment ID** page, and then select it in **Account receivable parameters**. A payment ID is a unique identifier for customer payments that are settled electronically. It can be divided into different parts, such as the customer account number, invoice number, prefix, suffix, and external reference. When you receive a payment from a customer, the payment ID identifies the payment transaction for a sales invoice that is received from a bank.

## eInvoice and AvtaleGiro enrollment import
You receive a message to update payment defaults values for the corresponding customer account, specified in the <strong>Method of payment</strong> and <strong>Payment specification</strong> fields. This defines the characteristics of the export messages, generated for this customer account in the future. A set of rules intended to be executed while importing the file should be specified on the <strong>Import file **page and can be defined on the **eInvoice integration types</strong> page. In different cases, you can apply different integration types. Specific rules should be specified on the <strong>eInvoice Payment mode change</strong> page. The rules can be specified based on message <strong>Status</strong>, such as Active for subscription messages, Deleted for subscription cancelations, and Warning if the payer requires written notification attributes. This requires payment specifications to be defined for the selected method of payment. On the <strong>eInvoice enrollment and answer</strong> page, you can view imported eInvoice messages. To confirm that enrollment messages are received, you can generate answer messages when enrollments are ready for posting. Post the enrollments for the customer account updates to take effect. For AvtaleGiro messages, payment mode changes are applied during the file import process.





[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
