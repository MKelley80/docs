---
tap: "hubspot"
version: "2.0"

name: "companies"
doc-link: http://developers.hubspot.com/docs/methods/companies/get_company
singer-schema: https://github.com/singer-io/tap-hubspot/blob/master/tap_hubspot/schemas/companies.json
description: |
  The `companies` table contains info about the companies your HubSpot contacts belong to.

replication-method: "Full Table"
api-method:
  name: getACompany
  doc-link: https://developers.hubspot.com/docs/methods/companies/get_company

attributes:
## Primary Key
  - name: "companyId"
    type: "integer"
    primary-key: true
    description: "The ID of the company."

  - name: "portalId"
    type: "integer"
    alias: "portal-id"
    description: "The ID of the portal the company is associated with."
---
