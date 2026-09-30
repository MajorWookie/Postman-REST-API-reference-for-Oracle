# Oracle OpenAPI → Postman conversion report

Generated 2026-09-30T17:42:15.829Z by `pipeline/build.js` (openapi-to-postmanv2 6.3.3, swagger2openapi 7.0.8). Output: 28 collections in `Collections/`, 2 environments in `Environments/`, this report and `report.json` (the same numbers in machine-readable form) in the repo root.

## 1. Sources

| Key | Type | Title | Spec version | Size | Paths with operations | Operation-less path items | Operations | Schema repairs (type spellings / boolean required / $ref repaired / $ref dropped) | Undeclared path placeholders | Converter warnings |
|---|---|---|---|---|---|---|---|---|---|---|
| cxcpq | Swagger 2.0 | REST API Services for Oracle CPQ | 2026.03.27 | 4.3 MB | 668 | 0 | 974 | — / 0 / 0 / 0 | 1 | 0 |
| fasrp | OpenAPI 3 | REST API for Oracle Fusion Cloud SCM | 2026.06.29 | 287.5 MB | 6148 | 26 | 10335 | Integer×7, int64×5 / 0 / 0 / 0 | 560 | 0 |
| farca | OpenAPI 3 | REST API for Common Features in Oracle Fusion Cloud Applications | 2026.08.27 | 4.5 MB | 386 | 0 | 485 | — / 0 / 0 / 0 | 0 | 0 |
| farfa | OpenAPI 3 | REST API for Oracle Fusion Cloud Financials | 2026.08.27 | 96.5 MB | 1413 | 1 | 2277 | — / 0 / 2 / 0 | 16 | 0 |
| faaps | OpenAPI 3 | REST API for Sales and Fusion Service in Oracle Fusion Cloud Customer Experience | 2026.09.30 | 206.0 MB | 6201 | 6 | 9590 | — / 0 / 2 / 2 | 144 | 0 |

"Undeclared path placeholders" = `{param}` placeholders in a path key that the spec never declares as an `in: path` parameter (e.g. fasrp `{serialsUniqID8}` while only `serialsUniqID` is declared). They are still emitted as `:param` path variables, just without a description — a source-spec omission reproduced faithfully.
- cxcpq: `bomItemVarName` ×1
- fasrp: `DeliveryDetailInterfaceId4` ×66, `DeliveryDetailInterfaceId7` ×65, `RatePlanId2` ×51, `RatePlanChargeId2` ×40, `ShipmentLine2` ×29, …
- farfa: `ExpenseId2` ×14, `ApplicationId2` ×2
- faaps: `ChargePuid2` ×20, `SubscriptionContactId2` ×20, `BillLinePuid2` ×16, `UserActionId2` ×15, `UserActionId3` ×12, …

fasrp: 26 path item(s) declare no HTTP method at all (only a `servers` entry) and therefore yield no request — e.g. `/supplyChainPlans/{PlanId}/child/PlanningTables/{TableId}/enclosure/TableDefinition`, `/supplyChainPlans/{PlanId}/child/PlanningTables/{TableId}/child/Data/{Filter}/enclosure/Filter`, `/receivingReceiptTransactionRequests/{InterfaceTransactionId}/child/ASNLineDFF/{receivingReceiptTransactionRequests_ASNLineDFF_Id}`.

farfa: 1 path item(s) declare no HTTP method at all (only a `servers` entry) and therefore yield no request — e.g. `/erpProcesses/{OperationName}`.

faaps: 6 path item(s) declare no HTTP method at all (only a `servers` entry) and therefore yield no request — e.g. `/customerWorkOrders/action/setIbAssetIdViewCriteria`, `/customerWorkOrders/action/setWoParentIdViewCriteria`, `/customerWorkOrders/{WoNumber}/action/submitCancelPartsLines`.

Every operation of every source is accounted for: the pipeline fails if a converted request cannot be mapped back to its source operation, if any operation is missing, or if the per-source request total differs from the operation count.

## 2. Request count per collection

| # | Collection | File | Source | Requests | Folders (before → after flattening) | Root items | Same-name siblings | Size | Schema v2.1.0 |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Oracle CPQ | `Oracle_CPQ.postman_collection.json` | cxcpq | 974 | 119 → 110 | 49 | 20 | 17.2 MB | PASS |
| 2 | SCM – Inventory Management | `SCM_Inventory_Management.postman_collection.json` | fasrp | 3401 | 1055 → 1001 | 168 | 189 | 76.4 MB | PASS |
| 3 | SCM – Maintenance | `SCM_Maintenance.postman_collection.json` | fasrp | 639 | 163 → 158 | 51 | 40 | 12.3 MB | PASS |
| 4 | SCM – Manufacturing | `SCM_Manufacturing.postman_collection.json` | fasrp | 1180 | 369 → 327 | 52 | 100 | 25.5 MB | PASS |
| 5 | SCM – Order Management | `SCM_Order_Management.postman_collection.json` | fasrp | 1533 | 393 → 378 | 57 | 10 | 39.7 MB | PASS |
| 6 | SCM – Product Lifecycle Management | `SCM_Product_Lifecycle_Management.postman_collection.json` | fasrp | 1358 | 333 → 317 | 52 | 20 | 27.1 MB | PASS |
| 7 | SCM – Supply Chain Planning | `SCM_Supply_Chain_Planning.postman_collection.json` | fasrp | 1726 | 573 → 566 | 124 | 4 | 39.1 MB | PASS |
| 8 | SCM – Unclassified | `SCM_Unclassified.postman_collection.json` | fasrp | 498 | 131 → 125 | 3 | 14 | 8.8 MB | PASS |
| 9 | Fusion Common | `Fusion_Common.postman_collection.json` | farca | 447 | 122 → 114 | 44 | 0 | 6.7 MB | PASS |
| 10 | Fusion List of Values | `Fusion_List_of_Values.postman_collection.json` | farca | 38 | 22 → 22 | 19 | 0 | 0.6 MB | PASS |
| 11 | FIN – Receivables | `FIN_Receivables.postman_collection.json` | farfa | 269 | 94 → 89 | 19 | 4 | 5.2 MB | PASS |
| 12 | FIN – Payables | `FIN_Payables.postman_collection.json` | farfa | 230 | 63 → 61 | 20 | 0 | 4.8 MB | PASS |
| 13 | FIN – Expenses | `FIN_Expenses.postman_collection.json` | farfa | 272 | 90 → 85 | 29 | 2 | 6.0 MB | PASS |
| 14 | FIN – General Ledger | `FIN_General_Ledger.postman_collection.json` | farfa | 194 | 59 → 53 | 13 | 4 | 4.3 MB | PASS |
| 15 | FIN – Cash Management | `FIN_Cash_Management.postman_collection.json` | farfa | 122 | 30 → 28 | 11 | 0 | 2.1 MB | PASS |
| 16 | FIN – Joint Venture Management | `FIN_Joint_Venture_Management.postman_collection.json` | farfa | 555 | 149 → 144 | 43 | 4 | 11.4 MB | PASS |
| 17 | FIN – Federal Financials | `FIN_Federal_Financials.postman_collection.json` | farfa | 263 | 54 → 54 | 27 | 0 | 4.1 MB | PASS |
| 18 | FIN – List of Values | `FIN_List_of_Values.postman_collection.json` | farfa | 218 | 111 → 107 | 111 | 2 | 4.1 MB | PASS |
| 19 | FIN – Unclassified | `FIN_Unclassified.postman_collection.json` | farfa | 154 | 49 → 48 | 32 | 4 | 9.8 MB | PASS |
| 20 | CX – Customer Data Management | `CX_Customer_Data_Management.postman_collection.json` | faaps | 1076 | 251 → 245 | 14 | 0 | 21.6 MB | PASS |
| 21 | CX – Sales | `CX_Sales.postman_collection.json` | faaps | 1965 | 477 → 460 | 65 | 12 | 35.6 MB | PASS |
| 22 | CX – Partner Relationship Management | `CX_Partner_Relationship_Management.postman_collection.json` | faaps | 970 | 226 → 216 | 10 | 0 | 18.2 MB | PASS |
| 23 | CX – Service | `CX_Service.postman_collection.json` | faaps | 1777 | 406 → 387 | 96 | 18 | 59.1 MB | PASS |
| 24 | CX – Subscription Management | `CX_Subscription_Management.postman_collection.json` | faaps | 1748 | 411 → 400 | 103 | 2 | 37.4 MB | PASS |
| 25 | CX – Incentive Compensation | `CX_Incentive_Compensation.postman_collection.json` | faaps | 427 | 121 → 118 | 49 | 0 | 9.0 MB | PASS |
| 26 | CX – Contracts | `CX_Contracts.postman_collection.json` | faaps | 588 | 133 → 124 | 8 | 14 | 10.5 MB | PASS |
| 27 | CX – List of Values | `CX_List_of_Values.postman_collection.json` | faaps | 535 | 253 → 247 | 191 | 30 | 11.2 MB | PASS |
| 28 | CX – Unclassified | `CX_Unclassified.postman_collection.json` | faaps | 504 | 134 → 129 | 35 | 4 | 8.4 MB | PASS |

"Same-name siblings" counts requests that share name + method with another request in the same folder (Postman allows this; it is mostly caused by Oracle reusing summaries such as "GET action not supported", and by one-request folders being flattened into a common parent). Examples:

- Oracle CPQ: BOM Item Setups :: Validate BOM Item Tree [POST] × 2
- Oracle CPQ: Pricing Setup / Pricing Attributes :: Update Pricing Attribute Mappings [PATCH] × 2
- SCM – Inventory Management: Available Quantity Details :: GET action not supported [GET] × 2
- SCM – Inventory Management: Cycle Count Transactions / Count Lines / Flexfields for Count Lines :: GET action not supported [GET] × 2
- SCM – Maintenance: Installed Base Assets / Image Attachments / Large Object (LOB) Attributes - FileContents :: Delete a FileContents [DELETE] × 2
- SCM – Maintenance: Installed Base Assets / Image Attachments / Large Object (LOB) Attributes - FileContents :: Get a FileContents [GET] × 2
- SCM – Manufacturing: Discrete Work Orders / Active Operations for Work Orders / Attachments / Large Object (LOB) Attributes - FileContents :: Delete a FileContents [DELETE] × 2
- SCM – Manufacturing: Discrete Work Orders / Active Operations for Work Orders / Attachments / Large Object (LOB) Attributes - FileContents :: Get a FileContents [GET] × 2
- SCM – Order Management: Initialization Parameters - Deprecated :: Create one parameter [POST] × 2
- SCM – Order Management: Initialization Parameters - Deprecated :: Get all parameters [GET] × 2
- SCM – Product Lifecycle Management: Cross-Reference Relationships / Descriptive Flexfields :: Create descriptive flexfields [POST] × 2
- SCM – Product Lifecycle Management: Cross-Reference Relationships / Descriptive Flexfields :: Get all descriptive flexfields [GET] × 2
- SCM – Supply Chain Planning: Publish PAR Policies :: GET action not supported [GET] × 2
- SCM – Supply Chain Planning: Replenishment Policy Assignment Sets / Policy Segment Parameters :: GET action not supported [GET] × 2
- SCM – Unclassified: List of Values / Generic Value Set Values :: Get [GET] × 3
- SCM – Unclassified: List of Values / Generic Value Set Values :: Get all [GET] × 3
- FIN – Receivables: Receivables Disputes / Receivables Dispute Lines :: GET action not supported [GET] × 2
- FIN – Receivables: Receivables Disputes :: GET action not supported [GET] × 2
- FIN – Expenses: Expense Audit Predictions :: GET action not supported [GET] × 2
- FIN – General Ledger: Chart of Accounts Filters / Filter Criteria :: GET action not supported [GET] × 2
- FIN – General Ledger: Chart of Accounts Filters :: GET action not supported [GET] × 2
- FIN – Joint Venture Management: Joint Venture Accounting Headers / Joint Venture Distributions :: Get a joint venture distribution for the joint venture journal [GET] × 2
- FIN – Joint Venture Management: Joint Venture Accounting Headers / Joint Venture Distributions :: Get all joint venture distributions for the joint venture journal [GET] × 2
- FIN – List of Values: Generic Value Set Values :: Get all [GET] × 2
- FIN – Unclassified: SAFT-PT Encryption Keys :: GET action not supported [GET] × 2
- FIN – Unclassified: Tax Partner Registrations :: GET action not supported [GET] × 2
- CX – Sales: Activities / Large Object (LOB) Attributes - Description :: Get a Description [GET] × 2
- CX – Sales: Sales Machine Learning Models / Machine Learning Job Statistics Details :: Create a selected field [POST] × 2
- CX – Service: Assets :: Get all assets [GET] × 2
- CX – Service: Assets :: Get an asset [GET] × 2
- CX – Subscription Management: Subscription Grouping Rule Sets / Subscription Grouping Rules :: Get a subscription grouping rule [GET] × 2
- CX – Contracts: Contracts / Attachments / Large Object (LOB) Attributes - FileContents :: Delete a FileContents [DELETE] × 2
- CX – Contracts: Contracts / Attachments / Large Object (LOB) Attributes - FileContents :: Get a FileContents [GET] × 2
- CX – List of Values: Bill to Locations :: Get a bill-to location [GET] × 2
- CX – List of Values: Bill to Locations :: Get all bill-to locations [GET] × 2
- CX – Unclassified: Product Lifecycle Management / Item Catalogs / Attachments :: Check in one catalog attachment [POST] × 2
- CX – Unclassified: Product Lifecycle Management / Item Catalogs / Attachments :: Update the version of the attachment [POST] × 2

Environments: `CPQ.postman_environment.json`, `Fusion.postman_environment.json`.

## 3. Partitioning of the large Fusion specs

### fasrp (SCM)

Leading `/`-delimited tag segments found in the SCM spec and where they were routed:

| Leading tag segment | Operations | Target collection |
|---|---|---|
| Inventory Management | 3401 | SCM_Inventory_Management |
| Supply Chain Planning | 1726 | SCM_Supply_Chain_Planning |
| Order Management | 1533 | SCM_Order_Management |
| Product Lifecycle Management | 1358 | SCM_Product_Lifecycle_Management |
| Manufacturing | 1180 | SCM_Manufacturing |
| Maintenance | 639 | SCM_Maintenance |
| SCM Common | 403 | **SCM – Unclassified** |
| Sustainability | 79 | **SCM – Unclassified** |
| List of Values | 16 | **SCM – Unclassified** |

**SCM – Unclassified** received 498 operations from 3 leading segment(s): `SCM Common` (403), `Sustainability` (79), `List of Values` (16).

**Product Management → PLM mapping:** confirmed. The pipeline maps both `Product Management` and `Product Lifecycle Management` to **SCM – Product Lifecycle Management**. The spec's actual leading segment is `Product Lifecycle Management` (1358 ops); `Product Management` occurs 0 times.

Untagged operations: 0

Multi-tag operations (first tag used for routing/folders): 0

### farfa (Financials)

The Financials spec tags operations by top-level resource (e.g. `Alternate Name Mapping Rules/…`), not by product area, and neither the spec nor Oracle's documentation groups resources by area. Operations are therefore routed by a curated map of top-level resource names (`lib/partition.js`): List of Values first (tag contains "List of Values" or the resource ends in LOV — the Fusion List of Values rule), then exact resource names, then name patterns; any other resource goes to **FIN – Unclassified**. Folders keep the full tag path (the resource is the top-level folder); only a leading `List of Values` segment is dropped inside the List-of-Values collection.

| Collection | Operations | Top-level resources (operations) |
|---|---|---|
| FIN – Receivables | 269 | Alternate Name Mapping Rules (5), AutoInvoice Interface Lines (11), Bill Management Users (3), Collection Promises (6), Collections Delinquencies (4), Collections Strategies (15), Credit Data Point Values (4), Credit Data Points (4), Debit Authorizations (6), Receipt Method Assignments (5), Receipt Methods (4), Receivables Adjustments (4), Receivables Credit Memos (56), Receivables Customer Account Activities (20), Receivables Customer Account Site Activities (20), Receivables Disputes (6), Receivables Invoices (70), Salesperson Reference Accounts (4), Standard Receipts (22) |
| FIN – Payables | 230 | Early Payment Offers (16), External Payees (8), Income Tax Types (2), Interim Payables Documents (5), Invoice Approvals and Notifications History (2), Invoice Holds (8), Invoice Tolerances (2), Invoices (80), Netting Agreements (29), Payables and Procurement Options (2), Payables Calendar Types (4), Payables Distribution Sets (4), Payables Income Tax Regions (2), Payables Interface Invoices (26), Payables Invoice Holds (2), Payables Options (2), Payables Payments (21), Payment Process Requests (3), Payment Terms (8), Tax Reporting Entities (4) |
| FIN – Expenses | 272 | Expense Accommodations Polices (4), Expense Airfare Policies (4), Expense Audit Predictions (3), Expense Business Unit Settings (2), Expense Cash Advances (18), Expense Conversion Rate Options (4), Expense Credit Card Transactions (2), Expense Delegations (4), Expense Descriptive Flexfield Contexts (2), Expense Descriptive Flexfield Segments (2), Expense Distributions (8), Expense Entertainment Policies (4), Expense Locations (2), Expense Meals Policies (4), Expense Mileage Policies (4), Expense Miscellaneous Policies (4), Expense Per Diem Calculations (3), Expense Per Diem Policies (6), Expense Persons (2), Expense Preferences (5), Expense Preferred Types (2), Expense Profile Attributes (2), Expense Reports (72), Expense Scanned Images (3), Expense System Options (2), Expense Templates (12), Expense Travel Itineraries (12), Expense Types (8), Expenses (72) |
| FIN – General Ledger | 194 | Attribute Derivation Mapping Sets (20), Attribute Derivation Rules (5), Budgetary Control for Enterprise Performance Management Budget Transactions (6), Budgetary Control Results (2), Budgetary Control Results Budget Impacts (2), Budgetary Control Results for Enterprise Performance Management Budget Transactions (2), Chart of Accounts Filters (6), Currency Rates (2), Intercompany Agreements (74), Intercompany Transaction Source Documents (17), Journal Batches (36), Ledger Balances (2), Subledger Accounting Mapping Sets (20) |
| FIN – Cash Management | 122 | Bank Account User Rules (4), Bank Accounts (38), Bank Branches (5), Banks (5), Cash Bank Account Transfers (4), Cash Pools (10), External Bank Accounts (25), External Cash Transactions (17), Foreign Exchange FX Revaluation Setups (5), Foreign Exchange FX Transfer Setups (5), Instrument Assignments (4) |
| FIN – Joint Venture Management | 555 | Carried Interest Payout Balances (2), Joint Venture Account Sets (34), Joint Venture Accounting Headers (16), Joint Venture Approval Counts (2), Joint Venture Assignment Rules (18), Joint Venture Basic General Ledger Distributions (8), Joint Venture Basic Generated Distributions (8), Joint Venture Basic Overhead Distributions (8), Joint Venture Basic Subledger Distributions (8), Joint Venture Carried Interest Agreements (33), Joint Venture Carried Interest Distributions (2), Joint Venture Carried Interest General Ledger Distributions (5), Joint Venture Carried Interest Generated Distributions (6), Joint Venture Carried Interest Overhead Distributions (3), Joint Venture Carried Interest Penalties (10), Joint Venture Carried Interest Subledger Distributions (5), Joint Venture Distributions (5), Joint Venture General Ledger Distribution Totals (2), Joint Venture General Ledger Distributions (12), Joint Venture General Ledger Transaction Totals (2), Joint Venture General Ledger Transactions (13), Joint Venture Generated Distributions (8), Joint Venture Generated Transactions (10), Joint Venture Invoicing Partners (9), Joint Venture Operational Measure Types (9), Joint Venture Operational Measures (10), Joint Venture Operational States (9), Joint Venture Options (8), Joint Venture Overhead Distributions (8), Joint Venture Overhead Methods (26), Joint Venture Overhead Transactions (10), Joint Venture Partner Contribution Requests (9), Joint Venture Partner Contributions (26), Joint Venture Periodic Adjustment Factors (18), Joint Venture Project Sets (38), Joint Venture Source Transactions (18), Joint Venture Status Counts (2), Joint Venture Subledger Accounting Distribution Totals (2), Joint Venture Subledger Accounting Transaction Totals (2), Joint Venture Subledger Distributions (12), Joint Venture Subledger Transactions (13), Joint Venture Transactions (6), Joint Ventures (100) |
| FIN – Federal Financials | 263 | Federal Account Attributes (10), Federal Account Symbols (10), Federal Agency Location Codes (10), Federal Attribute Supplemental Rules (25), Federal Attributes (5), Federal Budget Execution Controls (10), Federal Budget Transaction Types (20), Federal Business Event Type Codes (10), Federal CTA FBWT Account Definitions (5), Federal DATA Act Balances (15), Federal DATA Act File Criteria (5), Federal DATA Act File Sequences (5), Federal Fund Attributes (10), Federal Groups (10), Federal GTAS Accumulation Balances (2), Federal Ledger Options Setup (14), Federal Payment Format Mappings (10), Federal SAM Account Address Sets (5), Federal SAM Trading Partner Business Units (5), Federal SAM Trading Partner Details (12), Federal Setup Options (10), Federal Transaction Data (3), Federal Treasury Account Symbols (20), Federal Treasury Confirmation Payments (2), Federal Treasury Confirmation Schedules (11), Federal Treasury Offset Amounts (5), Federal USSGL Accounts (14) |
| FIN – List of Values | 218 | List of Values (218) |
| FIN – Unclassified | 154 | Brazilian Fiscal Documents (2), Data Security for Users (4), Document Sequence Derivations (5), ERP Business Events (3), ERP Data Integrations (11), ERP Integrations (3), ERP Processes (1), Lease Accounting Payment Items (3), Party Fiscal Classifications (8), Party Tax Profiles (4), Revenue Contracts (16), Routing Results (6), SAFT-PT Encryption Keys (4), Source Document Additional Sublines (Spectra) (6), Source Document Lines (3), Standalone Selling Prices (Spectra) (6), Tax Authority Profiles (2), Tax Exemptions (4), Tax Intended Uses (2), Tax Partner Registrations (3), Tax Product Categories (2), Tax Registrations (4), Tax Transaction Business Categories (2), Taxpayer Identifiers (4), Third Party Fiscal Classifications (4), Third Party Site Fiscal Classifications (4), Third-Party Site Tax Reporting Code Associations (4), Third-Party Tax Reporting Code Associations (4), Transaction Tax Lines (2), Validate Tax Configurations (2), Withholding Tax Lines (2), Workflow Notification Contents (24) |

List of Values: 218 operations by tag, 0 by LOV resource name only. Untagged: 0; multi-tag: 0.

Operations this spec shares with another spec (same method and resolved path; kept in both collections): fasrp 9, faaps 6.

### faaps (Sales and Service)

The Sales and Service spec tags operations by top-level resource (e.g. `Access Group Extension Rules/…`), not by product area, and neither the spec nor Oracle's documentation groups resources by area. Operations are therefore routed by a curated map of top-level resource names (`lib/partition.js`): List of Values first (tag contains "List of Values" or the resource ends in LOV — the Fusion List of Values rule), then exact resource names, then name patterns; any other resource goes to **CX – Unclassified**. Folders keep the full tag path (the resource is the top-level folder); only a leading `List of Values` segment is dropped inside the List-of-Values collection.

| Collection | Operations | Top-level resources (operations) |
|---|---|---|
| CX – Customer Data Management | 1076 | Accounts (330), Address Style Formats (4), Contact Content Associations (2), Contacts (253), DaaS Smart Data (7), Geography Zones (2), Households (267), Hub Organizations (113), Hub Persons (66), Non-Duplicate Records (4), Resolution Links (8), Resolution Requests (11), Similarity Configurations (4), Source System References (5) |
| CX – Sales | 1965 | Activities (132), Activity Templates (57), Attribute Predictions (5), Business Plans (168), Campaign Members (25), Campaigns (60), Catalog Product Groups (19), Catalog Products Items (19), Collaboration Actions (16), Collaboration Recipients (5), Collaborations (3), Competitors (2), Competitors Accounts (13), Contests (22), Conversation Messages (43), Conversations (10), Email Footer Templates (8), Email Templates (31), Forecasts (17), Goal Metric (6), Goals (30), Intelligence in Sales Features (13), Intelligence Onboarding Data Sufficiency Jobs (10), KPI (10), Lightbox Documents (35), Lightbox Presentation Session Feedback (5), Lightbox Presentation Sessions (11), Machine Learning Use Cases (34), Objectives (82), Opportunities (357), Price Book Headers (15), Product Group Products (4), Product Group Usages (13), Product Groups (47), Product Statuses (2), Product Structure Hierarchies (2), Product Structures (9), Product Template Mappings (4), Products (61), Quote and Order Lines (6), Sales Forecast Adjustments (5), Sales Forecast Dimension Metadata (5), Sales Forecast Dimensions (2), Sales Forecast Historic Metrics (4), Sales Forecast Metric Definitions (3), Sales Forecast Metric Source Dimension Mappings (5), Sales Forecast Metric Source Items (2), Sales Forecast Metric Sources (21), Sales Forecast Parameters (3), Sales Forecast Participants (2), Sales Forecast Periods (2), Sales Forecast Quotas (5), Sales Forecasts Metrics (2), Sales Insights (9), Sales Leads (296), Sales Machine Learning Models (44), Sales Orders (40), Sales Promotions (5), Sales Suggestions (17), Sales Territories (31), Sales Territory Proposals (5), Scoring Models (10), Territories for Sales (21), Web Activities (2), Web Activity Rules (13) |
| CX – Partner Relationship Management | 970 | Budgets (102), Claims (114), Deal Registrations (144), MDF Requests (94), Partner Contacts (89), Partner Programs (70), Partner Tiers (11), Partners (250), Program Benefits (30), Program Enrollments (66) |
| CX – Service | 1777 | Action Events (4), Action Plans (28), Action Status Conditions (5), Action Templates (15), Actions (15), Assets (132), Assets Operation Access (2), Cases (120), Categories (5), Channels (15), Chat Authentications (3), Chat Conversations (5), Chat Details (18), Chat Interactions (10), Chat Transcripts (6), Consolidated Assets (2), Consumer Chat Details (18), Customer Account with Technician Preferences (2), Customer Self-Service Users (9), Dynamic Link Patterns (5), Dynamic Link Values (5), Email Verifications (5), Escalation Levels (5), Escalations (5), Field Groups (16), Field Service Connections (5), Field Service Schedulers (20), HR Helpdesk Service Requests (178), Inbound Message Filters (5), Inbound Messages (64), Interactions (98), Internal Service Requests (178), Link Templates (10), Link Types (5), Links (5), Maintenance (72), Milestones (6), Multi Channel Adapter Events (7), Multi-Channel Adapter Toolbars (10), My Self-Service Roles (2), Object Capacities (5), Omnichannel Events (2), Omnichannel Presence and Availability (6), Omnichannel Properties (5), Outbound Messages (20), Passive Beacon Service Statuses (4), Phone Calls (16), Phone Transcript Messages (8), Phone Verifications (5), Queues (22), Resource Capacities (5), Resource Loads (3), Self-Service Registrations (4), Self-Service Role Mappings (4), Self-Service Roles (5), Self-Service Users (9), Serialized Assets (2), Service Activities (2), Service AI Agent Metrics (Spectra) (8), Service Business Units (Spectra) (8), Service Details (2), Service Lookup Properties (Spectra) (9), Service Lookup Type Relations (Spectra) (12), Service Profiles (38), Service Providers (12), Service Request Summarizations (Spectra) (6), Service Request Tags (Spectra) (6), Service Requests (176), Signatures (8), SmartText Folders (10), SmartText History (5), SmartText User Variables (5), SmartTexts (11), Social Posts (13), Social Users (4), Survey Configurations (10), Survey Requests (11), Surveys (26), Tags (11), Technician Preferences (5), Technician Preferences View (2), Technician's Access Hours (5), Technician's Access Hours Adjusted for Overrides (2), Technician's Access off Days (5), Technician's Access off Days Adjusted for Overrides (2), Technician's Access Schedules (18), Universal Work Objects (16), Work Order Activity Types (7), Work Order Activity Types for Oracle Fusion Field Service (7), Work Order Area Configurations (5), Work Order Links (4), Work Order Statuses (7), Work Orders (27), Work Skill Conditions Configuration Keys (5), Work Zone Configuration Keys (5), Wrap Ups (17) |
| CX – Subscription Management | 1748 | Accounting Rules (2), Bill Line Transaction Types (2), Bill-to Accounts (2), Bill-to Contacts (2), Bill-to Sites (2), Billing Adjustments (10), Business Units (2), Close Credit Methods (2), Conversion Rate Types (2), Coverage Charge Discounts Adjustment Types (2), Coverage Charge Discounts Bill Types (2), Covered Asset Groups (2), Covered Customer Accounts (2), Covered Level Products (2), Covered Parties (2), Covered Party Sites (2), Covered Product Groups (2), Currencies (2), Definition Organizations (2), Document Subtypes (2), Entitlement Plan Charge Definitions (2), Entitlement Plan Estimate Charge Definitions (2), Entitlement Plan Related Charge Definitions (2), Entitlement Types (2), Entitlements (11), External Contacts (2), Formula Charges (5), Formula Libraries (5), Formula Plans (30), Formula Rate Variables (5), Formula Steps (5), Invoice Rules (2), Items (2), Languages (2), Legal Entities (2), Matrix Names (2), Metric Types (5), Milestone Templates (12), Output Tax Classifications (2), Party Roles (2), Payment Methods (2), Payment Sets (2), Payment Terms (2), Preventive Maintenance Programs (2), Preview Subscriptions (27), Price Adjustment Categories (5), Price Units of Measure (2), Pricing Basis (2), Pricing Components (2), Pricing Term Methods (2), Primary Parties (2), Related Items (2), Sales Credit Types (2), Sales Representatives (2), Ship-to Accounts (2), Ship-to Parties (2), Ship-to Party Sites (2), Standard Coverages (11), Subscription Accounts (47), Subscription Accounts Roles (5), Subscription AI Alerts (14), Subscription AI Features (5), Subscription Asset Transactions (13), Subscription Balance Codes (42), Subscription Balance Condition Criteria (4), Subscription Balance Profiles (37), Subscription Balance Registers (98), Subscription Callback Events (13), Subscription Coverage Exceptions (16), Subscription Coverage Schedules (21), Subscription Entitlement Assignments (22), Subscription Entitlement Plans (32), Subscription Grouping Rule Sets (31), Subscription Metric Insights (8), Subscription Metrics (2), Subscription Order Transactions (3), Subscription Parties (2), Subscription Price Adjustment Variables (39), Subscription Product Grouping Assignments (1), Subscription Products (226), Subscription Profile Balance Codes (2), Subscription Profile Billing Days (2), Subscription Templates (2), Subscription Usage Entitlements (36), Subscription Usage Event Batches (48), Subscription Usage Event Error Keys (2), Subscription Usage Event Errors (2), Subscription Usage Event Queues (14), Subscription Usage Event Types (18), Subscription Usage Events (13), Subscription Usage Rating Determinants (21), Subscription Utilities (5), Subscriptions (653), Tax Exempt Certificates (2), Tax Exempt Controls (2), Tier Headers VO (5), Tier Lines VO (5), Time Unit of Measures (2), Time Units of Measure (2), Transaction Types (2), Unit of Measures (2), Users (2), Warehouses (2) |
| CX – Incentive Compensation | 427 | Compensation Estimation Insights (4), Compensation Plans (51), Credit Categories (5), Incentive Compensation Calculation Simulations (22), Incentive Compensation Calculation Transaction Fields (2), Incentive Compensation Credit Details (2), Incentive Compensation Earnings (2), Incentive Compensation Expressions (13), Incentive Compensation Individual Credits (2), Incentive Compensation Individual Earnings (2), Incentive Compensation Participant Earnings by Plans (2), Incentive Compensation Participant Plan Assignments (2), Incentive Compensation Payee Credits (2), Incentive Compensation Payee Earnings (2), Incentive Compensation Periods (2), Incentive Compensation Plan Earnings (2), Incentive Compensation Plan Participant Earnings (2), Incentive Compensation Plan Statistics (2), Incentive Compensation Revenue by Credit Categories (2), Incentive Compensation Rule Hierarchies (25), Incentive Compensation Rule Qualifying Criteria (2), Incentive Compensation Rules by Participant (2), Incentive Compensation Search Payees (2), Incentive Compensation Summarized Credits (2), Incentive Compensation Summarized Earnings (2), Incentive Compensation Summarized Earnings Per Intervals (2), Incentive Compensation Summarized Table Configurations (5), Incentive Compensation Summarized Team Credits (2), Incentive Compensation Team Credits (2), Incentive Compensation Transactions (12), Participant Attainment Details (2), Participant Compensation Plans (34), Participant Credit Details (2), Participant Goal Details (2), Participant Rate Table Details (2), Participant Simulations (18), Participants (21), Pay Groups (15), Payment Batches (16), Payment Plans (15), Payment Transactions (5), Paysheets (8), Performance Measures (41), Plan Components (26), Rate Dimensions (10), Rate Tables (15), Roles (10), Service Request Credit Details (2), Service Request Earning Details (2) |
| CX – Contracts | 588 | Contract Asset Transactions (6), Contract KeyTerm Prompts (11), Contract Requests (34), Contract Type Prompts (2), Contracts (485), Key Terms (Spectra) (45), Library Clauses (3), Sections (2) |
| CX – List of Values | 535 | List of Values (515), Maintenance (16), SCM Common (2), Terms Template LOV (2) |
| CX – Unclassified | 504 | Access Group Extension Rules (10), Access Group Rules (21), Access Groups (9), Action Bar Configurations (3), Action Bar Synonyms (5), Application Usage Insights (17), Copy Maps (2), Deleted Records (2), Device Tokens (5), Export Activities (20), Feed Configurations (45), Import Activities (7), Import Activity Maps (10), Import Export Objects Metadata (5), Integration Instances (Spectra) (9), Integration Maps (Spectra) (6), Notification Followers (5), Object Link Types (5), Object Links (5), Object Metadata (29), Orchestration Supported Objects (5), Orchestrations (82), Process Metadata (5), Product Lifecycle Management (39), Recent Items (5), Resource Roles (2), Resource Users (7), Resources (8), Rollups (2), Setup Assistants (84), User Context Data Sources (3), User Context Object Types (26), User Favorites (5), User Relevant Items (6), Validation Report Rules (5) |

List of Values: 533 operations by tag, 2 by LOV resource name only (`GET /fscmRestApi/resources/11.13.18.05/termsTemplatesLOV`, `GET /fscmRestApi/resources/11.13.18.05/termsTemplatesLOV/{termsTemplatesLOVUniqID}`). Untagged: 0; multi-tag: 0.

Operations this spec shares with another spec (same method and resolved path; kept in both collections): fasrp 140, farca 5, farfa 6.

## 4. farca (Fusion Common) partitioning

| Bucket | Operations |
|---|---|
| Fusion List of Values — by tag containing "List of Values" | 32 |
| Fusion List of Values — by resource/path ending in LOV only | 6 |
| **Fusion List of Values total** | **38** |
| **Fusion Common** | **447** |

Operations classified List-of-Values by path/resource only (no "List of Values" tag): `GET /api/boss/data/objects/ora/commonAppsInfra/objects/v1/setEnabledLookupCodes/$views/lookupLOV`, `POST /api/boss/data/objects/ora/commonAppsInfra/objects/v1/setEnabledLookupCodes/$views/lookupLOV/$query`, `GET /api/boss/data/objects/ora/commonAppsInfra/objects/v1/commonLookupCodes/$views/lookupLOV`, `POST /api/boss/data/objects/ora/commonAppsInfra/objects/v1/commonLookupCodes/$views/lookupLOV/$query`, `GET /api/boss/data/objects/ora/commonAppsInfra/objects/v1/standardLookupCodes/$views/lookupLOV`, `POST /api/boss/data/objects/ora/commonAppsInfra/objects/v1/standardLookupCodes/$views/lookupLOV/$query`.

Untagged: 0; multi-tag: 0.

## 5. CPQ tokenization

Placeholders mapped to environment tokens (§8.3): `{Stage}`→`{{Stage}}`, `{ProcessVarName}`→`{{ProcessVarName}}`, `{MainDocVarName}`→`{{MainDocVarName}}`, `{subDocVarName}`→`{{SubDocVarName}}`, `{prodFamVarName}`→`{{prodFamVarName}}`, `{prodLineVarName}`→`{{prodLineVarName}}`, `{modelVarName}`→`{{prodModelVarName}}`.

Resolved-literal **concatenated commerce segments** tokenized (the §8.3 concatenated-form rule applied to the resolved literal, since the spec ships `commerceDocumentsOraclecpqoTransaction` rather than `commerce{Stage}{ProcessVarName}{MainDocVarName}`):

- `commerceDocumentsOraclecpqoTransaction → commerce{{Stage}}{{ProcessVarName}}{{MainDocVarName}}` × 82

Whole-segment resolved literals substituted by the §8.4 fallback guard (longest value first, whole segment only):

- none (no CPQ path contains a whole-segment literal value in this spec version)

Segments that *contain* one of the literal values but were deliberately left alone (not a whole-segment match):

- `versionTransaction_t` × 1

`{placeholder}` tokens still present after substitution — all genuine per-request path parameters, rendered as Postman `:param` path variables (or `{{var}}` collection variables where the placeholder is embedded inside a larger segment):

| Placeholder | Rendered as | Occurrences |
|---|---|---|
| `{id}` | `:id` | 171 |
| `{allProdFamsVarName}` | `:allProdFamsVarName` | 143 |
| `{attributeVarName}` | `:attributeVarName` | 114 |
| `{menuItemId}` | `:menuItemId` | 81 |
| `{processVarName}` | `:processVarName` | 50 |
| `{modelVariableName}` | `:modelVariableName` | 37 |
| `{agreementVariableName}` | `:agreementVariableName` | 35 |
| `{templateVariableName}` | `:templateVariableName` | 34 |
| `{ratePlanNumber}` | `:ratePlanNumber` | 27 |
| `{actionVarName}` | `:actionVarName` | 27 |
| `{companyLoginName}` | `:companyLoginName` | 26 |
| `{translationId}` | `:translationId` | 25 |
| `{priceItemId}` | `:priceItemId` | 23 |
| `{priceModelItemId}` | `:priceModelItemId` | 20 |
| `{priceAgreementItemId}` | `:priceAgreementItemId` | 20 |
| `{chargeGroupId}` | `:chargeGroupId` | 20 |
| `{docVarName}` | `:docVarName` | 20 |
| `{arraySetVarName}` | `:arraySetVarName` | 18 |
| `{modelId}` | `:modelId` | 16 |
| `{priceId}` | `:priceId` | 15 |
| `{bomItemVarName}` | `:bomItemVarName` | 15 |
| `{documentNumber}` | `:documentNumber` | 15 |
| `{ruleVariableName}` | `:ruleVariableName` | 14 |
| `{attributeVariableName}` | `:attributeVariableName` | 13 |
| `{taskId}` | `:taskId` | 13 |
| `{companyName}` | `:companyName` | 13 |
| `{languageCode}` | `:languageCode` | 12 |
| `{lookupTypeVarName}` | `:lookupTypeVarName` | 12 |
| `{groupVarName}` | `:groupVarName` | 12 |
| `{identifier}` | `:identifier` | 12 |
| `{imageId}` | `:imageId` | 12 |
| `{variableName}` | `:variableName` | 11 |
| `{tableName}` | `:tableName` | 10 |
| `{userName}` | `:userName` | 10 |
| `{rateCardVariableName}` | `:rateCardVariableName` | 8 |
| `{pricingMatrixVariableName}` | `:pricingMatrixVariableName` | 8 |
| `{tableName}` | `{{tableName}}` | 8 |
| `{resourceVarName}` | `:resourceVarName` | 8 |
| `{partyNumber}` | `:partyNumber` | 7 |
| `{lookupCode}` | `:lookupCode` | 6 |
| `{descriptionsId}` | `:descriptionsId` | 6 |
| `{category}` | `:category` | 6 |
| `{ruleId}` | `:ruleId` | 6 |
| `{bsId}` | `:bsId` | 5 |
| `{name}` | `:name` | 5 |
| `{companyLogin}` | `:companyLogin` | 5 |
| `{namespace.variableName}` | `:namespace_variableName` | 5 |
| `{layoutVarName}` | `:layoutVarName` | 4 |
| `{folderVarName}` | `:folderVarName` | 4 |
| `{lookupType}` | `:lookupType` | 4 |
| `{_row_number}` | `:_row_number` | 4 |
| `{key}` | `:key` | 3 |
| `{filterId}` | `:filterId` | 3 |
| `{lookupId}` | `:lookupId` | 3 |
| `{conditionId}` | `:conditionId` | 3 |
| `{code}` | `:code` | 3 |
| `{bomItemMapVarName}` | `:bomItemMapVarName` | 3 |
| `{rowId}` | `:rowId` | 3 |
| `{fieldName}` | `:fieldName` | 3 |
| `{searchId}` | `:searchId` | 3 |
| `{arraySetVarName}` | `{{arraySetVarName}}` | 3 |
| `{trainingId}` | `:trainingId` | 2 |
| `{chargeId}` | `:chargeId` | 2 |
| `{settingId}` | `:settingId` | 2 |
| `{integrationVarName}` | `:integrationVarName` | 2 |
| `{DataTable}` | `{{DataTable}}` | 2 |
| `{rootId}` | `:rootId` | 2 |
| `{commerceProcessVarName}` | `:commerceProcessVarName` | 1 |
| `{dataSourceVariableName}` | `:dataSourceVariableName` | 1 |
| `{docNumber}` | `:docNumber` | 1 |
| `{matrixDataId}` | `:matrixDataId` | 1 |
| `{userLoginName}` | `:userLoginName` | 1 |
| `{childVarName}` | `:childVarName` | 1 |
| `{processId}` | `:processId` | 1 |
| `{docId}` | `:docId` | 1 |
| `{xslVarName}` | `:xslVarName` | 1 |
| `{pfVar}` | `:pfVar` | 1 |
| `{plVar}` | `:plVar` | 1 |
| `{modelVar}` | `:modelVar` | 1 |
| `{ruleConditionIndex}` | `:ruleConditionIndex` | 1 |
| `{ruleSelectionIndex}` | `:ruleSelectionIndex` | 1 |
| `{dataStoreName}` | `:dataStoreName` | 1 |
| `{mainDocVarName}` | `:mainDocVarName` | 1 |
| `{segmentVarName}` | `:segmentVarName` | 1 |
| `{personalizationName}` | `:personalizationName` | 1 |
| `{productId}` | `:productId` | 1 |
| `{fileName}` | `:fileName` | 1 |
| `{exportAttachmentActionVarName}` | `:exportAttachmentActionVarName` | 1 |
| `{copyToFavoritesActionVarName}` | `:copyToFavoritesActionVarName` | 1 |
| `{lockActionVarName}` | `:lockActionVarName` | 1 |
| `{displayHistoryActionVarName}` | `:displayHistoryActionVarName` | 1 |
| `{subitemId}` | `:subitemId` | 1 |
| `{conditionIndex}` | `:conditionIndex` | 1 |
| `{customerId}` | `:customerId` | 1 |

Params left as `:var` (91): `id`, `allProdFamsVarName`, `attributeVarName`, `menuItemId`, `processVarName`, `modelVariableName`, `agreementVariableName`, `templateVariableName`, `ratePlanNumber`, `actionVarName`, `companyLoginName`, `translationId`, `priceItemId`, `priceModelItemId`, `priceAgreementItemId`, `chargeGroupId`, `docVarName`, `arraySetVarName`, `modelId`, `priceId`, `bomItemVarName`, `documentNumber`, `ruleVariableName`, `attributeVariableName`, `taskId`, `companyName`, `languageCode`, `lookupTypeVarName`, `groupVarName`, `identifier`, `imageId`, `variableName`, `tableName`, `userName`, `rateCardVariableName`, `pricingMatrixVariableName`, `resourceVarName`, `partyNumber`, `lookupCode`, `descriptionsId`, `category`, `ruleId`, `bsId`, `name`, `companyLogin`, `namespace.variableName`, `layoutVarName`, `folderVarName`, `lookupType`, `_row_number`, `key`, `filterId`, `lookupId`, `conditionId`, `code`, `bomItemMapVarName`, `rowId`, `fieldName`, `searchId`, `trainingId`, `chargeId`, `settingId`, `integrationVarName`, `rootId`, `commerceProcessVarName`, `dataSourceVariableName`, `docNumber`, `matrixDataId`, `userLoginName`, `childVarName`, `processId`, `docId`, `xslVarName`, `pfVar`, `plVar`, `modelVar`, `ruleConditionIndex`, `ruleSelectionIndex`, `dataStoreName`, `mainDocVarName`, `segmentVarName`, `personalizationName`, `productId`, `fileName`, `exportAttachmentActionVarName`, `copyToFavoritesActionVarName`, `lockActionVarName`, `displayHistoryActionVarName`, `subitemId`, `conditionIndex`, `customerId`.

Embedded placeholders rendered as `{{var}}` collection variables: `tableName`, `arraySetVarName`, `DataTable`.

Path-variable keys renamed for Postman compatibility (Postman treats `.` as a separator inside `:var`): `{namespace.variableName}` → `:namespace_variableName`.

## 6. Sample request URLs (post-tokenization)

**Oracle CPQ**

- `{{baseUrl}}{{RestVersion}}/commerce{{Stage}}{{ProcessVarName}}{{MainDocVarName}}/:id/actions/copyLineItems_t`
- `{{baseUrl}}{{RestVersion}}/productFamilies/{{prodFamVarName}}/productLines/{{prodLineVarName}}/models/{{prodModelVarName}}/layouts/:layoutVarName`
- `{{baseUrl}}{{RestVersion}}/salesUsers/:key`

Collection variables (embedded placeholders): `DataTable`, `arraySetVarName`, `tableName`

**SCM – Inventory Management**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/shipmentLineChangeRequests/:TransactionId/child/shipmentLines/:shipmentLinesUniqID`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/shippingParameters/:OrganizationId`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/fndStaticLookups`

**SCM – Maintenance**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/assetGroupRules/:RuleId/child/usages/:RuleUsageId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/maintenanceRecommendations/:RecId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/partsShippingMethodsLOV/:partsShippingMethodsLOVUniqID`

**SCM – Manufacturing**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/productionLines/:ProductionLineId/child/PlLineOperation/:PlLineOperationId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/assetSystemOptions/:SystemOptionId`
- `{{baseUrl}}/api/scm-core/operational-data/v1/events`

**SCM – Order Management**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/channelAdjustmentTypes/:AdjustmentTypeId/child/adjustmentReasons/:AdjustmentReasonId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/pricingSegments/:MatrixRuleId`
- `{{baseUrl}}/fscmRestApi/cjmRest/channelCustomerProgramCheckbookBalances`

**SCM – Product Lifecycle Management**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/productConcepts/:ConceptId/child/Team/:TeamUniqID`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/productConcepts/:ConceptId`
- `{{baseUrl}}/hcmRestApi/resources/{{restVersion}}/rolesLOV`

**SCM – Supply Chain Planning**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/replenishmentPolicyAssignmentSetsV2/:PolicySetId/child/UnassignedSegmentLOV/:UnassignedSegmentLOVUniqID`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/productionSchedulingItemClasses/:ItemClassId`
- `{{baseUrl}}/fscmRestApi/backlogManagement/latest/backlogPlans/allocationMeasuresReports`

**SCM – Unclassified**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/b2bMessageTransactions/:MessageGUID/child/Attachments/:AttachmentsUniqID`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/b2bMessageParameters/:MsgParamId`
- `{{baseUrl}}/fscmRestApi/constraintProblem/solve`

**Fusion Common**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/standardLookups/:LookupType/child/lookupCodes/:LookupCode`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/features/:FeatureCode`
- `{{baseUrl}}/api/boss/data/objects/ora/commonAppsInfra/objects/v1/standardLookupTypes/$query`

Collection variables (embedded placeholders): `csId`

**Fusion List of Values**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/setIdSetsLOV/:setIdSetsLOV_Id`
- `{{baseUrl}}/api/boss/data/objects/ora/commonAppsInfra/objects/v1/setEnabledLookupCodes/$views/lookupLOV`
- `{{baseUrl}}/fndSetupApi/resources/{{restVersion}}/timezonesLOV/:TimezoneCode`

**FIN – Receivables**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/collectionPromises/:PromiseDetailId/child/collectionPromiseDFF/:PromiseDetailId2`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/collectionPromises/:PromiseDetailId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/collectionPromises/:PromiseDetailId/child/collectionPromiseDFF`

**FIN – Payables**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/payablesPaymentTerms/:termsId/child/payablesPaymentTermsLines/:payablesPaymentTermsLinesUniqID`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/payablesPaymentTerms/:termsId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/payablesPaymentTerms/:termsId/child/payablesPaymentTermsSets`

**FIN – Expenses**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/expenseAirfarePolicies/:AirfarePolicyId/child/expenseAirfarePolicyLines/:PolicyLineId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/expensePerDiemCalculations/:expensePerDiemCalculationsUniqID`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/expenseDffContexts/:RowIdentifier`

**FIN – General Ledger**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/intercompanyAgreements/:IntercompanyAgreementId/child/intercompanyAgreementDFF/:IntercompanyAgreementId2`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/attributeDerivationRules/:AttributeRuleId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/intercompanyAgreements/:IntercompanyAgreementId/child/transferAuthorizationGroups/:TransferAuthorizationGroupId/child/transferAuthorizationGroupDFF/:TransferAuthorizationGroupId2`

**FIN – Cash Management**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/cashBankAccounts/:BankAccountId/child/bankAccountPaymentDocuments/:PaymentDocumentId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/instrumentAssignments/:PaymentInstrumentAssignmentId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/fxRevaluationSetups/:fxRevaluationSetupsUniqID`

**FIN – Joint Venture Management**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/jointVentureSLADistributions/:distributionId/child/distributionDFF/:DistributionId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/jointVentureSLATransactionTotals/:jointVentureSLATransactionTotalsUniqID`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/jointVentureSLADistributions/:distributionId/child/Account`

**FIN – Federal Financials**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/fedAccountSymbols/:FedAccountSymbolId/child/fedAccountSymbolDFF/:FedAccountSymbolId2`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/fedAccountSymbols/:FedAccountSymbolId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/fedAccountSymbols/:FedAccountSymbolId/child/fedAccountSymbolDFF`

**FIN – List of Values**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/jointVentureSLASupportingReferencesLOV/:shortName`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/fndStaticLookups`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/customerAccountSitesLOV/:SiteUseId`

**FIN – Unclassified**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/partyFiscalClassifications/:ClassificationTypeId/child/fiscalClassificationTypeTaxRegimeAssociations/:fiscalClassificationTypeTaxRegimeAssociationsUniqID`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/taxExemptions/:TaxExemptionId`
- `{{baseUrl}}/api/boss/data/objects/ora/erpCore/revenueManagement/v1/revenueContractStandaloneSellingPrices/:revenueContractStandaloneSellingPrices_id/$query`

**CX – Customer Data Management**

- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/hubOrganizations/:PartyNumber/child/SourceSystemReference/:SourceSystemReferenceId`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/hubOrganizations/:PartyNumber`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/hubOrganizations/action/findDuplicates`

**CX – Sales**

- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/keyPerformanceIndicators/:KPINumber/child/KPIHistoryMetadata/:KPIEventId`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/collaborationRecipientLookups/:ResourceId`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/collaborationRecipientLookups`

**CX – Partner Relationship Management**

- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/mdfClaims/:ClaimCode/child/ClaimApprovalHistory/:VersionKey`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/mdfClaims/:ClaimCode`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/mdfClaims/:ClaimCode/child/ClaimResource/:ClaimResourceId/child/smartActions/:mdfClaims_ClaimResource_smartActions_Id`

**CX – Service**

- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/actions/:ActionNumber/child/actionAttribute/:ActionAttributeId`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/actions/:ActionNumber`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/actions`

**CX – Subscription Management**

- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/subscriptionGroupingRuleSets/:GroupingRuleSetNumber/child/subscriptionGroupingRules/:GroupingRuleNumber`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/billToContacts/:ContactId`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/billToContacts`

**CX – Incentive Compensation**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/participantCompensationPlans/:participantCompensationPlansUniqID/child/ParticipantCompensationPlansDFFs/:SrpCompPlanId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/incentiveCompensationPlanEarnings/:CompensationPlanId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/incentiveCompensationSummarizedTableConfigurations/:incentiveCompensationSummarizedTableConfigurationsUniqID`

**CX – Contracts**

- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/contracts/:contractsUniqID/child/Note/:NoteId`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/contracts/:contractsUniqID`
- `{{baseUrl}}/api/boss/data/objects/ora/cxSalesCommon/keyterms/v1/keyterms/$query`

**CX – List of Values**

- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/activityFunctionLookups/:activityFunctionLookupsUniqID/child/activityTypeLookup/:activityTypeLookupUniqID`
- `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/contractItemMasters/:OrganizationId`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/activitySubtypesLOV/:ActivitySubtypeId`

**CX – Unclassified**

- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/feedConfigurations/:FeedId/child/FeedSupportedObjects/:Id`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/sensingAgentConfigurations/:ConfigurationCode`
- `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/sensingAgentConfigurations`

## 7. Schema validation (Postman Collection v2.1.0)

| File | Result |
|---|---|
| `Oracle_CPQ.postman_collection.json` | PASS |
| `SCM_Inventory_Management.postman_collection.json` | PASS |
| `SCM_Maintenance.postman_collection.json` | PASS |
| `SCM_Manufacturing.postman_collection.json` | PASS |
| `SCM_Order_Management.postman_collection.json` | PASS |
| `SCM_Product_Lifecycle_Management.postman_collection.json` | PASS |
| `SCM_Supply_Chain_Planning.postman_collection.json` | PASS |
| `SCM_Unclassified.postman_collection.json` | PASS |
| `Fusion_Common.postman_collection.json` | PASS |
| `Fusion_List_of_Values.postman_collection.json` | PASS |
| `FIN_Receivables.postman_collection.json` | PASS |
| `FIN_Payables.postman_collection.json` | PASS |
| `FIN_Expenses.postman_collection.json` | PASS |
| `FIN_General_Ledger.postman_collection.json` | PASS |
| `FIN_Cash_Management.postman_collection.json` | PASS |
| `FIN_Joint_Venture_Management.postman_collection.json` | PASS |
| `FIN_Federal_Financials.postman_collection.json` | PASS |
| `FIN_List_of_Values.postman_collection.json` | PASS |
| `FIN_Unclassified.postman_collection.json` | PASS |
| `CX_Customer_Data_Management.postman_collection.json` | PASS |
| `CX_Sales.postman_collection.json` | PASS |
| `CX_Partner_Relationship_Management.postman_collection.json` | PASS |
| `CX_Service.postman_collection.json` | PASS |
| `CX_Subscription_Management.postman_collection.json` | PASS |
| `CX_Incentive_Compensation.postman_collection.json` | PASS |
| `CX_Contracts.postman_collection.json` | PASS |
| `CX_List_of_Values.postman_collection.json` | PASS |
| `CX_Unclassified.postman_collection.json` | PASS |

## 8. Environments

**CPQ** (`CPQ.postman_environment.json`): `CPQ UserName=(empty)`, `CPQ Password=(empty) [secret]`, `RestVersion=/rest/v19`, `Stage=Documents`, `ProcessVarName=Oraclecpqo`, `MainDocVarName=Transaction`, `SubDocVarName=TransactionLine`, `commerceProcessMainDocumentID=(empty)`, `documentId=(empty)`, `bsid=(empty)`, `documentNumber=(empty)`, `baseUrl=https://your-cpq-site.bigmachines.com`, `prodFamVarName=(empty)`, `prodLineVarName=(empty)`, `prodModelVarName=(empty)`, `exportedFileName=(empty)`, `uploadFileName=(empty)`

Defined for the user but not referenced by any generated URL or collection auth: `SubDocVarName`, `commerceProcessMainDocumentID`, `documentId`, `bsid`, `documentNumber`, `exportedFileName`, `uploadFileName`.

**Fusion** (`Fusion.postman_environment.json`): `baseUrl=https://your-fusion-host`, `restVersion=11.13.18.05`, `username=(empty) [secret]`, `password=(empty) [secret]`

Defined for the user but not referenced by any generated URL or collection auth: none.

## 9. Assumptions and judgment calls

- Collections are written to `Collections/`, environments to `Environments/`, and REPORT.md / report.json to the repo root (the layout of the published repo). An environment file whose content differs from the generated one only in `_postman_exported_at` is left untouched, so rebuilds do not churn it.
- fasrp: the spec's leading tag segment is `Product Lifecycle Management` (1358 ops), not `Product Management` (0 ops); both are mapped to SCM – Product Lifecycle Management.
- Most Fusion operations use bare resource path keys (e.g. `/inventoryTransactions`) with a base such as `/fscmRestApi/resources/11.13.18.05` declared as a path-level `servers` entry (fasrp 10310 of 10335, farca 31 of 485, farfa 2254 of 2277, faaps 9225 of 9590); the pipeline resolves op-level > path-level > spec-level `servers` into the URL before tokenizing, so results look like `{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/inventoryTransactions/:id` or `{{baseUrl}}/crmRestApi/resources/{{restVersion}}/accounts/:PartyNumber`. Keys lacking a leading `/` (e.g. `ess/rest/scheduler/…`) get one: fasrp 0, farca 19, farfa 0, faaps 0.
- The `11.13.18.05` version segment is replaced with `{{restVersion}}` wherever it appears as a whole segment, i.e. also outside `/fscmRestApi/resources/`: `/crmRestApi/resources` (7952 ops), `/fscmRestApi/scm` (1 ops), `/hcmRestApi/resources` (3 ops), `/fscmRestApi/fom` (1 ops), `/fndSetupApi/resources` (2 ops), `/crmRestApi/crmSalesIntelligenceApi` (9 ops). The Fusion environment sets restVersion=11.13.18.05, so the resolved URLs are identical to the spec. All Fusion collections — SCM, Common, Financials and Sales and Service — share the one Fusion environment (`baseUrl` is the pod host; each URL carries its own API root).
- Host stripping covers `http://servername/…`, `https://<servername>/…`, bare `<servername>/…`, `servername/…` and `https://host/…`, and prepends the missing `/` to keys like `ess/rest/scheduler/…`.
- Path keys are normalized *before* conversion (openapi-to-postmanv2 otherwise emits hosts like `{{baseUrl}}servername`); every operation is tagged with a hidden numeric op marker in its summary so each converted request maps back to exactly one source operation (verified; the marker is stripped from the output and the build fails if any remains).
- SCM – Unclassified keeps the leading tag segment as its top-level folders (`SCM Common`, `Sustainability`, `List of Values`) because that segment is not the collection name there; the six pillar collections drop it as specified.
- farca List-of-Values rule: "resource/path ends in LOV" is evaluated on the last segment that is neither a `{param}` nor a `$`-action/view suffix, so the `POST …/$views/lookupLOV/$query` advanced-query operations stay with their `GET …/$views/lookupLOV` siblings in Fusion List of Values (6 ops classified by path only: `GET /api/boss/data/objects/ora/commonAppsInfra/objects/v1/setEnabledLookupCodes/$views/lookupLOV`, `POST /api/boss/data/objects/ora/commonAppsInfra/objects/v1/setEnabledLookupCodes/$views/lookupLOV/$query`, `GET /api/boss/data/objects/ora/commonAppsInfra/objects/v1/commonLookupCodes/$views/lookupLOV`, `POST /api/boss/data/objects/ora/commonAppsInfra/objects/v1/commonLookupCodes/$views/lookupLOV/$query`, `GET /api/boss/data/objects/ora/commonAppsInfra/objects/v1/standardLookupCodes/$views/lookupLOV`, `POST /api/boss/data/objects/ora/commonAppsInfra/objects/v1/standardLookupCodes/$views/lookupLOV/$query`).
- farfa (Financials, 2277 ops) and faaps (Sales and Service, 9590 ops) tag operations by top-level resource, not by product area, and Oracle publishes no area grouping for them (the spec tags, the documentation table of contents and the "All REST Endpoints" page are all flat and alphabetical). They are split into product-area collections with a curated map of top-level resource names in `lib/partition.js` (`FIN_AREAS`, `CX_AREAS`; exact names win over patterns, validated by unit tests), because one collection per spec would be 52 MB and 211 MB — the latter over GitHub's 100 MB file limit. Anything not in the map goes to the source's Unclassified collection so a new Oracle resource is never dropped: FIN – Unclassified 154 ops (Brazilian Fiscal Documents (2), Data Security for Users (4), Document Sequence Derivations (5), ERP Business Events (3), ERP Data Integrations (11), ERP Integrations (3), ERP Processes (1), Lease Accounting Payment Items (3), Party Fiscal Classifications (8), Party Tax Profiles (4), Revenue Contracts (16), Routing Results (6), SAFT-PT Encryption Keys (4), Source Document Additional Sublines (Spectra) (6), Source Document Lines (3), Standalone Selling Prices (Spectra) (6), Tax Authority Profiles (2), Tax Exemptions (4), Tax Intended Uses (2), Tax Partner Registrations (3), Tax Product Categories (2), Tax Registrations (4), Tax Transaction Business Categories (2), Taxpayer Identifiers (4), Third Party Fiscal Classifications (4), Third Party Site Fiscal Classifications (4), Third-Party Site Tax Reporting Code Associations (4), Third-Party Tax Reporting Code Associations (4), Transaction Tax Lines (2), Validate Tax Configurations (2), Withholding Tax Lines (2), Workflow Notification Contents (24)); CX – Unclassified 504 ops (Access Group Extension Rules (10), Access Group Rules (21), Access Groups (9), Action Bar Configurations (3), Action Bar Synonyms (5), Application Usage Insights (17), Copy Maps (2), Deleted Records (2), Device Tokens (5), Export Activities (20), Feed Configurations (45), Import Activities (7), Import Activity Maps (10), Import Export Objects Metadata (5), Integration Instances (Spectra) (9), Integration Maps (Spectra) (6), Notification Followers (5), Object Link Types (5), Object Links (5), Object Metadata (29), Orchestration Supported Objects (5), Orchestrations (82), Process Metadata (5), Product Lifecycle Management (39), Recent Items (5), Resource Roles (2), Resource Users (7), Resources (8), Rollups (2), Setup Assistants (84), User Context Data Sources (3), User Context Object Types (26), User Favorites (5), User Relevant Items (6), Validation Report Rules (5)).
- farfa/faaps List of Values: the Fusion List of Values rule (tag contains "List of Values" or the resource ends in LOV) is applied before the area map, giving FIN – List of Values 218 ops and CX – List of Values 535 (2 of them by LOV resource name only, e.g. the `Maintenance/List of Values - Maintenance/…` lists, whose other Maintenance operations go to CX – Service). The leading `List of Values` tag segment is dropped as a folder inside these collections because it is the collection itself — the same treatment as the SCM pillar segment.
- CX – Customer Data Management holds the customer master (trading community) resources: `accounts`, `contacts`, `households`, `hubOrganizations`, `hubPersons`, plus duplicate resolution and source-system references. The similarly named `billToAccounts`, `billToContacts`, `billToSites`, `shipToAccounts`, `shipToParties`, `shipToPartySites`, `primaryParties`, `partyRoles`, `externalContacts` and `covered…` resources are, per their spec descriptions, lists of values scoped to subscriptions, so they are routed to CX – Subscription Management; `receivablesCustomerAccountActivities` / `…SiteActivities` (customer balances and activity) are in FIN – Receivables.
- Operations published by more than one spec (same method and resolved path) are kept in every collection that its spec produces — each collection mirrors its own spec: faaps shares fasrp 140, farca 5, farfa 6 ops (mostly SCM Maintenance and Product Lifecycle Management resources that the Sales and Service spec also documents), farfa shares fasrp 9, faaps 6.
- Root segments without a `…RestApi` or `/api` prefix are reproduced as the spec gives them: faaps `/customobjects` (2), `/usersessionmetrics` (1), `/userloginmetrics` (1), `/activity` (1), `/popflows` (1), `/timespent` (1), `/objectgrowthv2` (1), `/cumulativegrowth` (1), `/appInsightsLoginSma` (1), `/appInsightsSessionSma` (1), `/appInsightsClicksSma` (1), `/appInsightsObjectSma` (1), `/interactionObjectNames` (1), `/interactionscumulativegrowth` (1), `/quickfacts` (1), `/quickfactsCustomObject` (1), farfa none. The faaps "Application Usage Insights" operations (e.g. `/usersessionmetrics`) declare no `servers` base at all, so they become `{{baseUrl}}/usersessionmetrics`; Oracle documents no other root for them.
- faaps is fetched from `https://docs.oracle.com/en/cloud/saas/sales/faaps/openapi.json` — Oracle publishes the Sales and Service spec without a release segment (the `…/26c/…` form returns 404), so a re-fetch always pulls the current release (spec version 2026.09.30); farfa is pinned to 26C like fasrp and farca.
- CPQ: the spec contains none of `{Stage}`, `{ProcessVarName}`, `{MainDocVarName}`, `{subDocVarName}`; the commerce paths arrive resolved as `commerceDocumentsOraclecpqoTransaction` (82 ops), which is tokenized into `commerce{{Stage}}{{ProcessVarName}}{{MainDocVarName}}` by applying the §8.3 concatenated-form rule to the resolved literal (§8.4's whole-segment guard alone would not match it). No `…TransactionLine` / `{subDocVarName}` form exists in this spec version, so `{{SubDocVarName}}` is defined in the environment but unused; the sub-document appears only as the lower-case child segment `transactionLine` (17 ops), left literal because it differs in case from the SubDocVarName value. The `[Line]` handling in lib/urls.js is a guard for future spec versions.
- CPQ: placeholders that differ from the §8.3 names only by case — `{processVarName}` (50 ops), `{mainDocVarName}` (1 ops) — plus the abbreviated `{pfVar}`/`{plVar}`/`{modelVar}` and `{docVarName}`/`{commerceProcessVarName}` under the `/commerceProcesses/…` admin resources are treated as genuine per-request path parameters (`:param`), because §8.3 keys on exact placeholder names and §8.5 lists `{commerceProcessVarName}` as genuine.
- CPQ: `{{RestVersion}}` has the value `/rest/v19` (leading slash), so it is placed in the URL host part (`{{baseUrl}}{{RestVersion}}`) — Postman always inserts a `/` between host and path, and this keeps `raw` and `host`/`path` consistent (verified with postman-collection). Roots seen: `/rest/v19` (967 ops), `/cpq/rest/v19` (4 ops), `/rest/v18/products` (3 ops); `/cpq/rest/v19/…` becomes `{{baseUrl}}/cpq{{RestVersion}}/…` and `/rest/v18/…` is left literal because the rule only tokenizes `/rest/v19`.
- Placeholders embedded inside a larger path segment (e.g. `custom{DataTable}`, `config{prodFamVarName}.{prodLineVarName}.{modelVarName}`) cannot be Postman `:path` variables, so non-mapped ones become `{{name}}` collection variables declared (empty) on the collection.
- Path-variable keys containing characters Postman cannot bind (it splits `:var` at the first `.`) are renamed: `{namespace.variableName}` → `:namespace_variableName`; the original spec name is kept in the variable description.
- A placeholder repeated within one path (e.g. farca `…/{ProcessId}/child/…/{ProcessId}`) registers a single `:ProcessId` variable, because Postman binds one value per key: cxcpq 0, fasrp 0, farca 32, farfa 0, faaps 0 ops.
- Trailing slashes in source path keys are preserved as a trailing empty path segment (Postman renders `…/`): cxcpq 11, fasrp 0, farca 0, farfa 0, faaps 0 ops.
- farca: Oracle's path `<servername>/fscmUI/applcoreApi/v2/csm/import/status{csId}` is missing a `/` before `{csId}`; it is reproduced faithfully as `…/import/status{{csId}}` with `csId` declared as a collection variable (its sibling `…/export/status/{csId}` is a normal `:csId` path variable).
- Broken local `$ref`s (pointers that resolve to nothing) are repaired before conversion by `repairComposedRefs` in lib/spec-prep.js; otherwise the converter writes "reference … not found in the OpenAPI spec" into faked bodies. Oracle points some refs at a property of an `allOf`-composed schema as if it were flat; the property is looked up through the composition (`allOf/<n>` steps are not significant) and the ref is rewritten to the member that declares it. A ref whose property exists nowhere (Oracle's `Tag_item/properties/id` and `…/value`, where the schema's fields are `$id` / `$value`) is removed, leaving an empty schema for that field. farfa: 2 repaired (`oraErpCoreStructure.Ledger_item-fields/allOf/0/properties/ledgerId` → `oraErpCoreStructure.Ledger_item-fields/properties/ledgerId`), 0 dropped (—); faaps: 2 repaired (`oraCxServiceCoreSrMgmt.ServiceRequest_item/properties/number` → `oraCxServiceCoreSrMgmt.ServiceRequest_item-fields/properties/number`, `oraCxServiceCoreSrMgmt.ServiceRequest_item/properties/id` → `oraCxServiceCoreSrMgmt.ServiceRequest_item-fields/properties/id`), 2 dropped (`oraCxServiceCoreCommon.Tag_item/properties/value`, `oraCxServiceCoreCommon.Tag_item/properties/id`). Refs to external documents are left untouched — farfa 16, faaps 30 distinct, all pointing at Oracle-internal test hosts that are not reachable; the converter skips them, so the affected fields are simply absent from faked bodies.
- Converter faker placeholders inside faked JSON bodies are replaced with `null`: circular-reference markers (265 occurrences) and `"<Error: Too many levels of nesting to fake this schema>"` (cxcpq 0, fasrp 0, farca 0, farfa 61198, faaps 781924), which json-schema-faker emits for deeply recursive schemas — mainly the `/api/boss` ("Spectra") resources.
- Faked JSON bodies (request bodies, example responses and their original requests) longer than 512 KB are depth-capped by `capFakedJson` (lib/bodies.js): re-serialized at the deepest nesting level that still fits, with deeper objects/arrays emptied to `{}` / `[]`. The largest faked body of the CPQ/SCM/Common collections is ~309 KB, so only the recursive `/api/boss` ("Spectra") examples are affected — without this, CX – Service alone would be ~165 MB (its Internal Service Request and HR Helpdesk examples fake to ~8 MB each). Capped: 62 bodies (cxcpq 0, fasrp 0, farca 0, farfa 8, faaps 54); largest 8207 KB → 295 KB, kept depths 4–10.
- CPQ Swagger 2.0 was upconverted with swagger2openapi. Pre-conversion schema repairs (schema nodes only — example/enum/default payloads are never touched): property-level boolean `required` folded into the parent `required` array (cxcpq 0, fasrp 0, farca 0, farfa 0, faaps 0 properties); non-standard type spellings normalized (cxcpq none, fasrp Integer×7 int64×5, farca none, farfa none, faaps none).
- Collection-level `auth` is Basic with the environment tokens; every request inherits it (the converter's per-request `auth: null` is removed so requests show Postman's native "Inherit auth from parent").
- Request generation: bodies/examples are faked from the schema when the spec has no example (`parametersResolution: Example`). Optional query parameters and headers are generated **but disabled** (`enableOptionalParameters: false`) so a request is runnable as-is — Oracle rejects placeholder values such as `fields=string`; enable them in Postman as needed. Required parameters stay enabled. `REST-Framework-Version` headers (fasrp 19232, farca 350, farfa 4266, faaps 16216, counting request and example-request copies) are pinned to the highest value the spec's enum allows instead of a random faked value; the spec marks them optional, so they ship disabled. Not covered by the disable rule: optional fields of form-data/urlencoded bodies (19 CPQ requests) stay enabled with faked values. Faked values are placeholders only — path-variable and body values such as `string`, integers or floats from `type: number` params must be replaced before sending; example responses derived from OpenAPI `default` responses carry no status code (converter behaviour); response-example ids are stripped so rebuilds are byte-stable apart from faked values.
- Single-sub-folder chains are NOT collapsed (only one-request/zero-sub-folder leaf folders are), as specified; flipping that is a one-line predicate change in lib/folders.js.
- Folders and requests are sorted alphabetically (case-insensitive, numeric-aware) at every level — sub-folders first, then requests; requests with identical names keep their source-spec order. `pipeline/sort-collection.js <file>` applies the same ordering to a hand-edited collection in place.
- Collection file(s) not overwritten by this run (SKIP_WRITE): Oracle_CPQ, SCM_Inventory_Management, SCM_Maintenance, SCM_Manufacturing, SCM_Order_Management, SCM_Product_Lifecycle_Management, SCM_Supply_Chain_Planning, SCM_Unclassified, Fusion_Common, Fusion_List_of_Values — hand-maintained files (Oracle_CPQ carries hand-added File Operations requests) and published files kept as they are rather than regenerated with new faked values. The counts above describe the pipeline result for them, not the file on disk.

## 10. Converter warnings

**cxcpq**: 0 warning(s)

**fasrp**: 0 warning(s)

**farca**: 0 warning(s)

**farfa**: 0 warning(s)

**faaps**: 0 warning(s)
