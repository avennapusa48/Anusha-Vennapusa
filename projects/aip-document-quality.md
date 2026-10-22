# AIP Document Validation Workbench

Working validation demo · AIP extraction is a documented extension

Try deterministic validation of synthetic extracted fields, with an AIP implementation blueprint for document extraction and human review.

## Run
Serve this package directory with any static web server, then open projects/aip-document-quality.html. No install, API key, or backend is required.

## Architecture
Document → AIP extraction → Typed fields → Validation → Human review → Audit

## Implementation plan
1. Ingest synthetic documents and preserve source IDs and document-level access controls.
2. Configure an AIP extraction workflow in your environment, using an explicit JSON schema for submission_id, organization, requested_limit, and confidence.
3. Require source references for extracted values and keep missing fields null rather than guessing.
4. Validate the structured output before routing records into an operational application.
5. Send missing, invalid, or low-confidence outputs to a reviewer; save source, model version, prompt version, reviewer, and timestamp.
6. Use a labeled evaluation set to measure field accuracy, missing-field detection, and reviewer override frequency.

## Acceptance criteria
- Missing organization triggers review.
- A non-positive requested limit triggers review.
- Confidence below 0.85 triggers review.
- Valid fields pass the demo checks; a pass does not imply approval or model accuracy.

## Limitations
Synthetic data only. Browser prototype, not a production Foundry/AIP deployment. The retrieval demo uses keyword ranking, not embeddings or LLM generation. No real underwriting decision is made.

## Official documentation
- [Palantir AIP](https://www.palantir.com/docs/foundry/aip/overview/)
- [Pipeline Builder](https://www.palantir.com/docs/foundry/pipeline-builder/overview/)