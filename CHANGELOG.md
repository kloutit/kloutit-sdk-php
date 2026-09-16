# CHANGELOG

## v4.3.0 - 15/09/2026

### ADDED

- `updateCaseStatus` accepts `ALLEGED` (you sent the generated defense yourself) and `ACCEPTED` (stop defending the case), besides `WON` and `LOST`

### UPDATED

- Case models: `paymentProcessor` is writable on creation and lists every processor the API accepts

## v4.2.0 - 10/09/2026

### ADDED

- Service to resolve a case as won or lost (`updateCaseStatus`)
- Services to read the connection info and to list, subscribe and unsubscribe webhooks

### UPDATED

- Case models: payment processor and BIN number on creation, preferred defense language, liability shift, `PROCESSING_ERROR` chargeback reason, webhook event payload details
- Sector guides: parking and renting vehicle added, travel airline updated

## v2.1.0 - 22/08/2025

### ADDED

- Service to create a new case into Kloutit
- Service to download the case defense


### UPDATED

- Adds new properties to case model

## v2.0.0 - 14/02/2025

### ADDED

- Service to upload a file to an existing case
- Service to enrich case data into Kloutit
- Service to submit that a case has been fully updated
- Service to check if a case is still missing some fields to be fully completed
- Service to validate webhook event

### UPDATED

- Authentication to Kloutit now works with a single apiKey configuration

## v1.0.0 - 10/10/2024

Initial release publication.

- Obtain accessToken
- Create new case into Kloutit
