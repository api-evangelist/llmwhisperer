# LLMWhisperer (llmwhisperer)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
