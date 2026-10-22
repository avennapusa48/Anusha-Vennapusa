# Foundry Ontology Explorer

Working browser prototype · Foundry deployment blueprint

Explore synthetic insurance entities and linked documents in a browser prototype inspired by Foundry Ontology modeling.

## Run
Serve this package directory with any static web server, then open projects/foundry-ontology-explorer.html. No install, API key, or backend is required.

## Architecture
Synthetic submissions → Validation → Object types → Link types → Operational review

## Implementation plan
1. Create synthetic submission, organization, and document datasets with unique primary keys.
2. In Pipeline Builder or Code Repositories, normalize fields and validate foreign keys before publishing clean datasets.
3. Define Submission, Organization, and Document Object Types in Ontology Manager.
4. Create submittedBy and supportedBy Link Types using the validated identifiers.
5. Create a review Action with required actor, reason, and timestamp fields; configure permissions in the target environment.
6. Build a Workshop object table and detail view, then wire the review Action to an explicit user confirmation.

## Acceptance criteria
- Primary keys are unique and required fields are present.
- Every submission links to an existing organization.
- Every document references a known submission.
- Only authorized reviewers can execute the production review Action; all changes are auditable.

## Limitations
Synthetic data only. Browser prototype, not a production Foundry/AIP deployment. The retrieval demo uses keyword ranking, not embeddings or LLM generation. No real underwriting decision is made.

## Official documentation
- [Palantir Ontology](https://www.palantir.com/docs/foundry/ontology/overview/)
- [Palantir Workshop](https://www.palantir.com/docs/foundry/workshop/overview/)