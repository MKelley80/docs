---
tap: "zuora"
version: 1.0

name: "journalEntryItem"
doc-link: w
#singer-schema: 
description: |
  The `journalEntryItem` table contains information about journal entry items.

replication-method: "Key-based Incremental"
api-method:
  name:
  doc-link:

attributes:
  - name: "id"
    type: "string"
    primary-key: true
    description: "The journal entry item ID."

  - name: "updatedDate"
    type: "date-time"
    replication-key: true
    description: "The date when the journal entry item was last updated."

  - name: "accountingCodeId"
    type: "string"
    description: "The name of the accounting code associated with the journal entry item."

  - name: "accountingCodeType"
    type: "string"
    description: |
      The type of the accounting code associated with the journal entry item. Possible values are:

      - `AccountsReceivable`
      - `On-Account Receivable`
      - `Cash`
      - `OtherAssets`
      - `CustomerCashOnAccount`
      - `DeferredRevenue`
      - `SalesTaxPayable`
      - `OtherLiabilities`
      - `SalesRevenue`
      - `SalesDiscounts`
      - `OtherRevenue`
      - `OtherEquity`
      - `BadDebt`
      - `OtherExpenses`

  - name: "amount"
    type: "double"
    description: "The amount of the journal entry item in the transaction currency."

  - name: "createdById"
    type: "string"
    description: "The ID of the Zuora user who created the journal entry item."

  - name: "createdDate"
    type: "date-time"
    description: "The date when the journal entry item was created."

  - name: "deleted"
    type: "boolean"
    description: |
      **Only supported for the AQuA API.** If `true`, this record was deleted in Zuora.

  - name: "journalEntryId"
    type: "string"
    description: "The ID of the journal entry associated with the journal entry item."
    foreign-key: true

  - name: "journalRunId"
    type: "string"
    description: "The ID of the journal run associated with the journal entry item."
    foreign-key: true

  - name: "type"
    type: "string"
    description: "The type of journal entry item."

  - name: "updatedById"
    type: "string"
    description: "The ID of the Zuora user who last updated the journal entry item."

---