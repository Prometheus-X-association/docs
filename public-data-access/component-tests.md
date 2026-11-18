# Component-Level Test Expected Results

## Browsing and Understanding ESTAT Tables

To explore the available EUROSTAT (ESTAT) databases and construct queries for the Public Data Access BB:

- **Browse the list of all EUROSTAT databases:**
  - Visit: [EUROSTAT Database](https://ec.europa.eu/eurostat/data/database)
- **Find a specific table:**
  - Each database/table has a unique browser link. For example, the NAMA_10_GDP table: [NAMA_10_GDP Table](https://ec.europa.eu/eurostat/databrowser/view/nama_10_gdp/)
- **Filter and customize data:**
  - Use the "Customize" tab in the Eurostat Data Browser to visually select filters and dimensions (country, period, indicator, etc.).
  - The resulting SDMX query string (the part after the table code in the URL) can be copied and used in your API requests.
- **About SDMX syntax:**
  - Data filtering and selection in API requests is performed using the [SDMX](https://sdmx.org/?page_id=5008) (Statistical Data and Metadata eXchange) syntax. This syntax is visible in the Eurostat browser and is used to specify dimensions and filters for each table.
  - For example, in the request `/ESTAT/NAMA_10_GDP/A.CP_MEUR.B1GQ.LU?startPeriod=2023&endPeriod=2024&format=json`, the SDMX part is `A.CP_MEUR.B1GQ.LU`.

This approach allows you to visually explore available data, construct valid SDMX queries, and use them directly with the Public Data Access BB for programmatic access.


## Setup

Before running the component-level tests, ensure your environment is set up. You can refer to the Local Development Environment section in the README for full details. The essential steps are:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

This creates a virtual environment, activates it, and installs the required dependencies.

This document refines the expected results for manual component-level tests of the Public Data Access BB. For each test case, it specifies which fields or outputs should be checked to validate correct behavior.

## 1. EUROSTAT API Integration
- **Request:**
  - `curl "http://localhost:8000/ESTAT/NAMA_10_GDP/A.CP_MEUR.B1GQ.LU?startPeriod=2023&endPeriod=2024&format=json"`
- **Expected Checks:**
  - Response HTTP status: `200 OK`
  - Response body: JSON object with expected EUROSTAT data fields (e.g., `value`, `period`, `geo`, etc.)
  - No error message in response
  - Usage statistics: Entry for this endpoint and API key (if used) incremented in `config/usage_stats.json`
  - Log entry: New line in `logs/api_requests.log` with request details

## 2. Multi-Method Authentication
- **Request Examples:**
  - `curl -H "X-API-Key: ..." ...`
  - `curl -H "Authorization: Bearer ..." ...`
  - `curl ...?api_key=...`
- **Expected Checks:**
  - Response HTTP status: `200 OK` for valid keys, `401 Unauthorized` for invalid/missing keys
  - Response body: Valid JSON data for successful requests, error object for failures
  - Usage statistics: Correct API key usage incremented in `config/usage_stats.json`
  - Log entry: Authentication method and result recorded in `logs/api_requests.log`

## 3. Metadata Endpoints
- **Request:**
  - `/endpoints`, `/usage-stats`, `/`
- **Expected Checks:**
  - `/endpoints`: JSON array of available endpoints, each with `name`, `url`, and `description`
  - `/usage-stats`: JSON object with API key and open access usage counts (fields: `api_key`, `count`, etc.)
  - `/`: Service metadata (fields: `service_name`, `version`, `status`, etc.)
  - All responses: HTTP 200, valid JSON

## 4. Error Scenarios
- **Request:**
  - Nonexistent endpoint: `/NONEXISTENT`
- **Expected Checks:**
  - HTTP status: `404 Not Found` for missing endpoints, `401 Unauthorized` for missing/invalid authentication
  - Response body: JSON error object with fields: `error`, `message`, `status_code`
  - No update to usage statistics for failed requests
  - Log entry: Error details recorded

## 5. Logging
- **File:** `logs/api_requests.log`
- **Expected Checks:**
  - Each request (success or error) results in a new log entry
  - Log entry fields: timestamp, endpoint, status code, API key (if used), error (if any)

## 6. Usage Statistics
- **File:** `config/usage_stats.json`
- **Expected Checks:**
  - After each successful request, the corresponding usage count is incremented
  - Fields: `api_key` (or `open_access`), `count`, `last_access` (if present)

## 7. OpenAPI Documentation
- **Endpoint:** `/docs`
- **Expected Checks:**
  - Page loads successfully
  - All documented endpoints are present and match `/endpoints` output
  - Authentication examples are correct and functional

---

For each test, the tester should record the actual value of the checked field and compare it to the expected value or format above. This enables precise, repeatable validation for independent testers.
