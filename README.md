# Web Scraper & Supabase Data Automation with n8n

An automated workflow that collects e-commerce product information and stores structured records using **n8n, HTTP requests, HTML extraction, JavaScript, and Supabase**.

## Overview

Manually collecting product information from multiple website pages takes time and creates repetitive data-entry work.

This project demonstrates how to collect product links, retrieve individual product pages, extract relevant details, and save the results in a Supabase database.

The workflow processes products in batches and uses a Wait step to control the pace of execution. The recorded demonstration shows a Supabase table containing 830 product records.

## What the Workflow Does

- Starts execution through an n8n Schedule Trigger.
- Retrieves a source page using an HTTP Request.
- Extracts product links from HTML.
- Uses JavaScript to prepare product items.
- Processes individual product pages through a loop.
- Extracts product titles, prices, descriptions, and links.
- Maps the extracted information to database columns.
- Creates structured product records in Supabase.
- Uses a Wait step to control processing pace.

## Workflow Process

1. **Start the workflow.** Run the workflow manually for testing or through the configured Schedule Trigger.
2. **Prepare inputs.** Set the values needed for the source request and extraction steps.
3. **Fetch the source page.** Retrieve website content using an HTTP Request.
4. **Extract product links.** Use HTML extraction and JavaScript to prepare product URLs.
5. **Process products.** Loop through the product pages in batches.
6. **Extract product details.** Retrieve each product page and extract the required fields.
7. **Map fields.** Prepare the values for the corresponding Supabase columns.
8. **Store records.** Create product records in the destination table.
9. **Continue processing.** Wait for the configured interval before processing the next batch.

## Technology Stack

| Tool | Purpose |
| --- | --- |
| n8n | Workflow orchestration and scheduling |
| HTTP Request nodes | Retrieve source and product pages |
| HTML extraction | Extract product links and page content |
| JavaScript | Transform and prepare product data |
| Edit Fields | Map extracted values to destination fields |
| Loop Over Items | Process product items in batches |
| Wait | Control timing between batches |
| Supabase | Store structured product records |

## Data Stored

The demonstrated Supabase table includes the following fields.

| Field | Purpose |
| --- | --- |
| id | Database record identifier |
| title | Product name |
| price | Extracted product price |
| page_content | Prepared product content |
| product_url | Source product-page URL |
| description | Product description |
| image_url | Product image link |
| created_at | Record creation timestamp |

The table structure and field mappings can be adapted to the requirements of another product catalog.

## Demo

The demo shows the workflow processing product pages and saving the extracted information in Supabase.

It includes the n8n execution and a database table containing 830 records. Viewers can inspect product titles, prices, descriptions, image links, source URLs, and collection timestamps.

This is a personal portfolio demonstration.

## Business Applications

The stored product data can support the following applications.

- Structured product catalogs.
- Internal product research.
- Product reporting and analysis.
- Data preparation for downstream integrations.
- Product information workflows connected to other business tools.

Additional reporting, synchronization, or search features can be built around the stored records.

## Setup Requirements

To recreate or adapt this workflow, you need the following.

- An n8n instance.
- A Supabase project and destination table.
- An accessible source website you are authorized to collect data from.
- Extraction rules that match the website's HTML structure.
- Defined product fields and corresponding database columns.

Configure the Supabase credentials within n8n and verify that the destination table accepts the mapped values.

## Configuration and Testing

1. Set the source URL and target product pages.
2. Adjust HTML selectors for the listing and product-detail pages.
3. Review the JavaScript transformations.
4. Connect the Supabase credentials.
5. Configure the destination table and field mappings.
6. Set the batch size and waiting interval.
7. Test with a small sample of product pages.
8. Compare extracted values with the original source pages.
9. Verify the saved records in Supabase.
10. Configure scheduled execution after validating the results.

## Scope and Limitations

- Extraction rules depend on the source website's HTML structure.
- Website layout changes may require selector updates.
- Some pages may have missing prices, descriptions, or image links.
- Login-protected or dynamically rendered pages may require a different collection method.
- Repeated execution requires an agreed record-matching strategy to prevent unwanted duplicates.
- Hosting and database costs depend on your own accounts and usage.

## Credential Safety

Configure credentials inside n8n. Review workflow exports and screenshots before publishing them, and remove API keys, access tokens, passwords, and private data.

Only collect and use website content you are authorized to access.

## Author

**Haroon AI Automation**

Building practical n8n workflows, data integrations, and business automations.

## Project Status

Completed portfolio demo demonstrating product-link extraction, batch processing, product-detail collection, and structured storage in Supabase.

## Demo Video

[Watch the Web Scraper & Supabase Automation Demo](./Web-Scraper-Supabase-90s-With-Voice.mp4)
