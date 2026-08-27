# Postman REST API reference for Oracle

Ready-to-import **Postman Collection v2.1** files for Oracle Cloud REST APIs, generated programmatically from Oracle's published OpenAPI / Swagger specifications. Every operation in the source spec is present as a request, URLs are tokenized against a shared environment, and folders mirror Oracle's own tag hierarchy.

## What's included

| Collection | File | Source spec | Requests |
|---|---|---|---|
| Oracle CPQ | `Oracle_CPQ.postman_collection.json` | CPQ 2026.03.27 (Swagger 2.0) | 974 |
| SCM – Inventory Management | `SCM_Inventory_Management.postman_collection.json` | Fusion SCM 26C | 3,401 |
| SCM – Maintenance | `SCM_Maintenance.postman_collection.json` | Fusion SCM 26C | 639 |
| SCM – Manufacturing | `SCM_Manufacturing.postman_collection.json` | Fusion SCM 26C | 1,180 |
| SCM – Order Management | `SCM_Order_Management.postman_collection.json` | Fusion SCM 26C | 1,533 |
| SCM – Product Lifecycle Management | `SCM_Product_Lifecycle_Management.postman_collection.json` | Fusion SCM 26C | 1,358 |
| SCM – Supply Chain Planning | `SCM_Supply_Chain_Planning.postman_collection.json` | Fusion SCM 26C | 1,726 |
| SCM – Unclassified | `SCM_Unclassified.postman_collection.json` | Fusion SCM 26C | 498 |
| Fusion Common | `Fusion_Common.postman_collection.json` | Fusion Applications Common 26C | 447 |
| Fusion List of Values | `Fusion_List_of_Values.postman_collection.json` | Fusion Applications Common 26C | 38 |

Environments:

| Environment | File | Used by |
|---|---|---|
| CPQ | `CPQ.postman_environment.json` | Oracle CPQ |
| Fusion | `Fusion.postman_environment.json` | All SCM and Fusion collections |

Source specifications (Oracle Help Center):

- CPQ — <https://docs.oracle.com/en/cloud/saas/configure-price-quote/cxcpq/swagger.json>
- Fusion Cloud SCM — <https://docs.oracle.com/en/cloud/saas/supply-chain-and-manufacturing/26c/fasrp/openapi.json>
- Fusion Applications Common — <https://docs.oracle.com/en/cloud/saas/applications-common/26c/farca/openapi.json>

`REPORT.md` is the full conversion report: request counts, partitioning rules, tokenization tables, sample URLs, schema-validation results and every judgment call made during conversion.

## Getting started

1. In Postman choose **Import** and drop in the collection file(s) you need plus the matching environment file.
2. Select the environment and fill in:
   - **Fusion** — `baseUrl` (e.g. `https://your-pod.fa.us2.oraclecloud.com`), `username`, `password`. `restVersion` defaults to `11.13.18.05`.
   - **CPQ** — `baseUrl` (your `*.bigmachines.com` site), `CPQ UserName`, `CPQ Password`, and the commerce/product variable names for your site (`Stage`, `ProcessVarName`, `MainDocVarName`, `prodFamVarName`, `prodLineVarName`, `prodModelVarName`).
3. Open a request, set its path variables (`:id`, `:OrganizationId`, …) and send.

Authentication is **Basic** and set once at the collection level; every request inherits it from the environment's username/password variables.

> The SCM collections are large (up to ~75 MB). Import them one at a time, or only the pillars you work with.
>
> `SCM_Inventory_Management.postman_collection.json` is stored with **Git LFS**. Downloading it from the GitHub web UI works as usual; if you clone the repo, install [git-lfs](https://git-lfs.com) first (`git lfs install`) or you will get a small pointer file instead of the collection.

## URL conventions

Fusion collections:

```
{{baseUrl}}/fscmRestApi/resources/{{restVersion}}/inventoryTransactions/:id
{{baseUrl}}/api/boss/data/objects/ora/commonAppsInfra/objects/v1/commonLookupCodes/$views/lookupLOV
```

Oracle CPQ:

```
{{baseUrl}}{{RestVersion}}/commerce{{Stage}}{{ProcessVarName}}{{MainDocVarName}}/:id/actions/copyLineItems_t
{{baseUrl}}{{RestVersion}}/productFamilies/{{prodFamVarName}}/productLines/{{prodLineVarName}}/models/{{prodModelVarName}}/layouts/:layoutVarName
```

- OpenAPI `{param}` path parameters become Postman `:param` path variables registered on the request.
- Placeholders embedded inside a larger segment (e.g. `custom{DataTable}`) become `{{name}}` collection variables.
- Hosts are stripped; `11.13.18.05` is replaced by `{{restVersion}}`; `$query`, `$views` and similar segments are kept verbatim.

## Things to know before sending requests

- **Optional query parameters and headers are generated but disabled.** Oracle rejects placeholder values such as `fields=string`, so requests are runnable as-is; enable the parameters you need in Postman.
- Request bodies and example values are **faked from the schema** where the spec has no example. Replace `string` / numeric placeholders before sending.
- Folders follow Oracle's tags (`Resource / Child / Grandchild`); single-request leaf folders are flattened into their parent, and everything is sorted A→Z.
- A few requests share a name within a folder — Oracle reuses summaries such as "GET action not supported" — this is expected.
- Deprecated operations are included.

## How the collections are built

The files are produced by a Node pipeline (kept outside this repository) that fetches the specs, upconverts Swagger 2.0 with `swagger2openapi`, converts with `openapi-to-postmanv2`, partitions operations into the pillar collections by their leading tag segment, tokenizes URLs, rebuilds the folder tree from tags, and validates each collection against the Postman Collection v2.1.0 JSON schema. The pipeline fails if any source operation is missing from the output. Details and numbers are in `REPORT.md`.

Collections for other Oracle pillars (HCM, Financials, Procurement, CX Sales, PPM, …) from the previous hand-split generation of this repository are available in the git history.

## License

Collection files are derived from Oracle's public API documentation. Oracle and the product names above are trademarks of Oracle Corporation; this project is not affiliated with or endorsed by Oracle.
