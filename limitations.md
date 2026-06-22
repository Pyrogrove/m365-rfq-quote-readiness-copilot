# Limitations

This repository documents a portfolio prototype built with synthetic RFQ data. It demonstrates a controlled workflow pattern, not a production quotation system.

## Data and Security

* Synthetic data only
* No real customer, employee, pricing, commercial, or confidential data
* No production security assessment
* No formal data-loss-prevention or retention design
* No production role-based access model
* No secrets, tenant IDs, environment GUIDs, or connection identifiers included

## Workflow Scope

The prototype supports:

* controlled CSV intake
* deterministic validation
* exception classification
* review-owner assignment
* SharePoint status tracking
* file routing
* management visibility
* read-only Copilot retrieval
* bounded AI-assisted review

It does not include:

* ERP or CRM integration
* quotation generation
* pricing calculation
* stock or capacity confirmation
* order creation
* contract management
* payment processing
* production monitoring
* high-volume processing
* multilingual RFQ handling

## AI Boundary

The Copilot may:

* summarize an RFQ
* explain missing or ambiguous information
* draft clarification wording
* provide internal escalation guidance

The Copilot does not:

* calculate or issue prices
* approve discounts
* approve quotations
* promise delivery
* change deterministic workflow fields
* update SharePoint
* send customer replies
* mark a reply as sent
* approve its own output

The SharePoint record and Power Automate rules remain authoritative.

## Human Control

```text
HumanApprovalStatus = Approved
FinalReplySent = No
```

`Approved` means a human accepted an internal AI-generated draft for review purposes.

It does not mean the draft was sent to a customer.

Any production implementation would require an explicit approval and sending process with appropriate permissions, audit logging, and operational ownership.

## Input Constraints

The demo uses controlled, one-row CSV files.

The initial parser is not designed for:

* multi-row RFQ files
* complex quoted CSV values
* commas inside uncontrolled free-text fields
* OCR or unstructured-document extraction
* arbitrary email attachments
* malformed or hostile files

A production implementation would require stronger schema validation, file inspection, error handling, and input-channel controls.

## Platform and Licensing

The prototype depends on Microsoft 365, SharePoint, Power Automate, and Copilot Studio capabilities available in the authoring environment.

Licensing, connector availability, environment policy, capacity, and Copilot Studio publishing rights may differ between tenants.

These must be verified before production deployment.

## Reliability and Support

The prototype does not include:

* service-level commitments
* production support
* automated alerting
* formal retry strategy
* disaster recovery
* performance or load testing
* formal user acceptance testing
* deployment pipelines
* managed environment promotion
* production change control

The repository is intended to demonstrate solution design, workflow controls, test coverage, and safe AI boundaries.

