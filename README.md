# LLMWhisperer (llmwhisperer)

LLMWhisperer is a document-to-text extraction API from Unstract (Zipstack) that turns complex PDFs, scanned documents, and images into clean, layout-preserving text ready for large language models. It exposes an asynchronous REST API (v2) - submit a document to /whisper, poll /whisper-status, then retrieve the extracted text via /whisper-retrieve - plus line-level highlight coordinates and webhook callbacks. Authentication is via the unstract-key header.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/llmwhisperer/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/llmwhisperer/refs/heads/main/apis.yml)

## Tags

- AI
- LLM
- Document Extraction
- OCR
- Text Extraction

## Timestamps

- **Created:** 2026-06-20
- **Modified:** 2026-06-20

## APIs

### LLMWhisperer Whisper Extraction API

Submits a document (PDF, image, or URL) to POST /whisper for asynchronous, layout-preserving text extraction across native_text, low_cost, high_quality, form, and table modes. Returns a 202 with a whisper_hash used to track and retrieve the job.

- **Human URL:** [https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_text_extraction_api/](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_text_extraction_api/)
- **Base URL:** `https://llmwhisperer-api.us-central.unstract.com/api/v2`

#### Tags

- Extraction
- OCR
- Layout Preserving

#### Properties

- [Documentation](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_text_extraction_api/)
- [API Reference](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_apis_intro/)
- [OpenAPI](openapi/llmwhisperer-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/llmwhisperer.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/llmwhisperer.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### LLMWhisperer Whisper Status API

GET /whisper-status returns the processing state (accepted, processing, processed, error, retrieved) for a whisper_hash, with per-page execution detail.

- **Human URL:** [https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_text_extraction_status_api/](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_text_extraction_status_api/)
- **Base URL:** `https://llmwhisperer-api.us-central.unstract.com/api/v2`

#### Tags

- Status
- Async
- Polling

#### Properties

- [Documentation](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_text_extraction_status_api/)
- [OpenAPI](openapi/llmwhisperer-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/llmwhisperer.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/llmwhisperer.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### LLMWhisperer Whisper Retrieve API

GET /whisper-retrieve returns the extracted result_text plus optional confidence_metadata for a processed whisper_hash. Results can be retrieved once.

- **Human URL:** [https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_text_extraction_retrieve_api/](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_text_extraction_retrieve_api/)
- **Base URL:** `https://llmwhisperer-api.us-central.unstract.com/api/v2`

#### Tags

- Retrieve
- Results
- Text

#### Properties

- [Documentation](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_text_extraction_retrieve_api/)
- [OpenAPI](openapi/llmwhisperer-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/llmwhisperer.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/llmwhisperer.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### LLMWhisperer Highlights API

GET /highlights returns per-line bounding-box coordinates (base_y, height, page, page_height) for the requested lines so callers can highlight extracted text in the source document.

- **Human URL:** [https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_highlighting_api/](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_highlighting_api/)
- **Base URL:** `https://llmwhisperer-api.us-central.unstract.com/api/v2`

#### Tags

- Highlights
- Bounding Box
- Coordinates

#### Properties

- [Documentation](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_highlighting_api/)
- [OpenAPI](openapi/llmwhisperer-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/llmwhisperer.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/llmwhisperer.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### LLMWhisperer Webhooks API

Register and manage webhook callbacks via /whisper-manage-callback (POST/GET/PUT/DELETE). Submit a document with use_webhook to have the extracted result delivered to your endpoint instead of polling.

- **Human URL:** [https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_webhooks_manage/](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_webhooks_manage/)
- **Base URL:** `https://llmwhisperer-api.us-central.unstract.com/api/v2`

#### Tags

- Webhooks
- Callbacks
- Async

#### Properties

- [Documentation](https://docs.unstract.com/llmwhisperer/llm_whisperer/apis/llm_whisperer_webhooks_manage/)
- [OpenAPI](openapi/llmwhisperer-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Review](review.yml)
- [Postman Collection](collections/llmwhisperer.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/llmwhisperer.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/Zipstack)
- [LinkedIn](https://www.linkedin.com/company/unstract)
- [Website](https://unstract.com/llmwhisperer/)
- [Documentation](https://docs.unstract.com/llmwhisperer/)
- [Plans](plans/llmwhisperer-plans-pricing.yml)
- [Rate Limits](rate-limits/llmwhisperer-rate-limits.yml)
- [Fin Ops](finops/llmwhisperer-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
