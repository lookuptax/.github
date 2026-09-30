# LookupTax

**Global tax ID validation infrastructure for developers and businesses.**

[LookupTax](https://lookuptax.com/) provides a single API for validating **VAT numbers, GST numbers, EINs, ABNs, NZBNs, and other business tax identifiers** across 100+ countries.

We connect applications to country-specific tax authorities and official business registries, then expose the results through a consistent developer API.

**[Website](https://lookuptax.com/)** · **[API Documentation](https://lookuptax.com/docs)** · **[Supported Countries](https://lookuptax.com/countries)** · **[Pricing](https://lookuptax.com/pricing)** · **[Try LookupTax](https://lookuptax.com/)**

---

## What is LookupTax?

Global tax identity infrastructure is fragmented.

Every jurisdiction can have its own:

* Tax identification numbers
* VAT and GST registration systems
* Identifier formats and validation rules
* Government registries
* Validation APIs and protocols
* Authentication requirements
* Data availability and response semantics

LookupTax abstracts this country-specific complexity behind **one API for global tax ID validation**.

Instead of building and maintaining integrations with individual tax authorities and business registries, integrate with LookupTax once.

> **One API → global tax ID validation.**

[Learn more about global tax ID validation →](https://lookuptax.com/)

---

## Tax ID validation across 116 countries

LookupTax currently supports tax ID and VAT number validation across **116 countries**, with support for both official-source validation and syntax validation depending on the jurisdiction.

Supported tax identifier types include:

* VAT numbers
* GST numbers
* EIN / FEIN
* ABN
* NZBN
* Business registration numbers
* National tax identifiers
* Country-specific business tax IDs

Examples include:

**European Union:** VAT IDs across all 27 EU member states
**United Kingdom:** VAT and business identifiers
**United States:** EIN
**India:** GSTIN
**Australia:** ABN and GST
**New Zealand:** NZBN
**Canada:** Business Number and related identifiers
**Singapore:** UEN and GST
**Japan:** Corporate Number
**Mexico:** RFC
**Switzerland:** UID
**South Korea:** BRN
**Taiwan:** UBN

[See all supported countries and tax identifiers →](https://lookuptax.com/countries)

---

## Official-source tax ID validation

LookupTax is built around **official government and national registry sources** where validation is available.

Depending on the country, validation can connect to systems operated by tax authorities, business registries, and national validation services.

Examples include:

* European Commission VIES
* UK HMRC
* Australian Business Register
* India GST systems
* National business and tax registries across Europe
* Country-specific government validation services

LookupTax documents the validation source and country-specific behavior so developers can understand what a result actually means.

[Our approach to official-source validation →](https://lookuptax.com/our-approach-to-validation)

---

## Validation is not just `valid` or `invalid`

A tax identifier can have a correct format without being confirmed by an official registry. A registry can also be temporarily unavailable.

LookupTax therefore distinguishes between different validation outcomes.

| Status          | Meaning                                                                           |
| --------------- | --------------------------------------------------------------------------------- |
| `VALID`         | The tax ID was validated successfully and the entity was confirmed by a registry. |
| `INVALID`       | The identifier failed validation or no matching record was found.                 |
| `UNVERIFIED`    | The format was checked, but no queryable registry was available.                  |
| `INDETERMINATE` | The registry was temporarily unavailable; the request can be retried.             |
| `UNSUPPORTED`   | The country or identifier type is not currently supported.                        |

This distinction is particularly important for applications handling **customer onboarding, supplier onboarding, billing, invoicing, marketplaces, tax compliance, and business verification**.

The official Python SDK documents these statuses and recommends branching on `result.status` rather than treating all format-valid results as registry-confirmed.

---

## Built for developers

LookupTax is API-first and provides official SDKs for popular programming languages.

### Python

[LookupTax Python SDK →](https://github.com/lookuptax/lookuptax-sdk-python)

```bash
pip install lookuptax
```

[Package on PyPI →](https://pypi.org/project/lookuptax/)

### JavaScript / TypeScript

[LookupTax JavaScript / TypeScript SDK →](https://github.com/lookuptax/lookuptax-sdk-javascript)

```bash
npm install @lookuptax/sdk
```

[Package on npm →](https://www.npmjs.com/package/@lookuptax/sdk)

### Go

[LookupTax Go SDK →](https://github.com/lookuptax/lookuptax-sdk-go)

### .NET

[LookupTax .NET SDK →](https://github.com/lookuptax/lookuptax-sdk-dotnet)

[Browse all LookupTax repositories →](https://github.com/lookuptax)

---

## Simple REST API

LookupTax exposes a common API interface across supported countries.

Example:

```http
POST https://api.lookuptax.com/tax/validate
Content-Type: application/json

{
  "taxId": "DE123456789",
  "countryIso": "DE"
}
```

The API returns structured validation results and, where available and permitted by the underlying source, business information such as registered name and address.

[Read the LookupTax API documentation →](https://lookuptax.com/docs)

---

## Batch tax ID validation

For larger datasets, LookupTax supports batch validation for workflows such as:

* Supplier database cleansing
* Customer data migration
* Marketplace seller onboarding
* ERP migrations
* Tax data audits
* Large-scale tax ID verification

Batch validation supports large datasets and can return validation results and available business details for each record.

[Learn about bulk tax ID validation →](https://lookuptax.com/use-cases/bulk-tax-id-validation)

---

## AI and MCP

LookupTax also provides an **MCP server** that allows AI assistants and MCP-compatible clients to validate tax IDs without building a separate integration layer.

The MCP interface exposes tax ID validation tools and uses the same API authentication model as the REST API.

[See the latest LookupTax capabilities →](https://lookuptax.com/changelog)

---

## Common use cases

### Customer onboarding

Validate customer tax IDs during signup and account creation.

[Customer tax ID validation →](https://lookuptax.com/)

### Supplier onboarding

Verify supplier and vendor tax identifiers before adding them to procurement or accounts-payable systems.

### Invoice validation

Validate buyer and seller tax IDs before generating invoices.

[Invoice tax ID validation →](https://lookuptax.com/use-cases/invoice-validation)

### SaaS billing

Validate VAT, GST, EIN, and other tax identifiers as part of subscription billing and tax workflows.

[SaaS tax ID validation →](https://lookuptax.com/industries/saas-tax-validation)

### Marketplace seller verification

Use tax ID validation as part of seller onboarding and broader KYB workflows.

[Seller onboarding tax validation →](https://lookuptax.com/use-cases/seller-onboarding-tax-validation)

### Data cleansing and migration

Validate and clean existing customer, supplier, and business records at scale.

[Bulk tax ID validation →](https://lookuptax.com/use-cases/bulk-tax-id-validation)

### Cross-border B2B commerce

Validate tax IDs across jurisdictions when selling internationally and supporting VAT/GST compliance workflows.

[Cross-border tax compliance →](https://lookuptax.com/use-cases/cross-border-tax-compliance)

---

## Tax ID and compliance resources

LookupTax also publishes technical and educational resources covering **tax identification numbers, VAT, GST, tax compliance, e-invoicing, and country-specific requirements**.

### Country guides

Detailed guides covering tax ID formats, registration requirements, validation methods, and country-specific tax rules.

[Explore tax ID country guides →](https://lookuptax.com/docs/category/tax-identification-number)

### Tax ID verification guides

Country-specific information on how to verify VAT numbers, GST numbers, EINs, business numbers, and other tax identifiers.

[Explore tax ID verification guides →](https://lookuptax.com/docs/category/verify-tax-ids)

### Tax updates

Follow changes to tax rules, e-invoicing requirements, and country-specific compliance developments.

[Latest tax updates →](https://lookuptax.com/tax-updates/)

### Changelog

Track new countries, validation sources, API improvements, and developer capabilities.

[LookupTax changelog →](https://lookuptax.com/changelog)

### Blog

Research and commentary on tax technology, tax compliance, e-invoicing, SaaS taxation, and AI in tax infrastructure.

[LookupTax blog →](https://lookuptax.com/blog/)

---

## Why LookupTax?

Global tax ID validation looks simple from the outside.

In practice, every country has its own combination of identifiers, registries, validation rules, APIs, and operational constraints.

LookupTax handles that infrastructure so engineering teams can focus on the application layer.

**Integrate once. Validate tax identities globally.**

[Learn more about LookupTax →](https://lookuptax.com/)

---

## Developer resources

| Resource                    | Link                                                          |
| --------------------------- | ------------------------------------------------------------- |
| LookupTax website           | https://lookuptax.com/                                        |
| API documentation           | https://lookuptax.com/docs                                    |
| Supported countries         | https://lookuptax.com/countries                               |
| Pricing                     | https://lookuptax.com/pricing                                 |
| Python SDK                  | https://github.com/lookuptax/lookuptax-sdk-python             |
| JavaScript / TypeScript SDK | https://github.com/lookuptax/lookuptax-sdk-javascript         |
| Go SDK                      | https://github.com/lookuptax/lookuptax-sdk-go                 |
| .NET SDK                    | https://github.com/lookuptax/lookuptax-sdk-dotnet             |
| Python package              | https://pypi.org/project/lookuptax/                           |
| JavaScript package          | https://www.npmjs.com/package/@lookuptax/sdk                  |
| Tax ID country guides       | https://lookuptax.com/docs/category/tax-identification-number |
| Tax ID verification guides  | https://lookuptax.com/docs/category/verify-tax-ids            |
| Changelog                   | https://lookuptax.com/changelog                               |
| Blog                        | https://lookuptax.com/blog/                                   |

---

## Support

Need help integrating LookupTax, validating a specific tax identifier, or finding coverage for a country?

**Email:** [support@lookuptax.com](mailto:support@lookuptax.com)

For technical documentation and integration examples:

**[LookupTax API Documentation →](https://lookuptax.com/docs)**

For enterprise requirements, additional countries, or higher-volume validation:

**[Contact LookupTax →](mailto:support@lookuptax.com)**

---

## About LookupTax

LookupTax is building **tax identity infrastructure for global commerce**.

Our goal is to make tax and business registry infrastructure easier for software companies to integrate, operate, and scale across borders.

**Tax IDs → Business identity → Global commerce**

[Visit LookupTax →](https://lookuptax.com/)

---

**LookupTax — One API for global tax ID validation.**
