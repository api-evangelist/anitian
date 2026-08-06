# Anitian

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

Anitian, Inc. is a cloud security and compliance automation company (Portland, Oregon) that helps
SaaS providers reach and maintain U.S. federal compliance. Its **FedFlex** platform automates the
FedRAMP lifecycle — pre-engineered AWS and Azure landing zones, AI-driven evidence collection mapped
to FedRAMP 20x Key Security Indicators (KSIs) and NIST 800-53 controls, SSP generation, an auditor
view for 3PAOs, and continuous monitoring. Anitian merged with **Arkenstone Defense** in April 2026.

- Website: https://www.anitian.com/
- FedFlex platform: https://www.anitian.com/fedflex-platform-overview/
- GitHub: https://github.com/anitianinc

## API surface

Anitian publishes **no OpenAPI, GraphQL SDL, AsyncAPI, SDK, CLI, or developer portal**. Two live API
surfaces were found and both are gated:

| Surface | Host | Observed |
|---|---|---|
| SecureCloud / FedFlex Platform API | `securecloud.anitian.com/api` | 307 → `/auth/signin` on every path except `/api/health` and NextAuth `/api/auth/*`; federated to Okta + Amazon Cognito |
| FedFlex Copilot WebSocket API | `copilot.anitian.com` | 426 Upgrade Required over HTTP; WebSocket `$connect` returns 401 Unauthorized (AWS API Gateway, us-west-2) |

Anitian's own FedRAMP 20x README states *"an API is available for auditors to download evidence and
integrate it into their own systems"* — but neither the endpoint nor its credential model is
published.

## What Anitian does publish machine-readably

Its complete **FedRAMP 20x Phase One pilot submission** is public on GitHub — a KSI-aligned
assessment file (51 controls across 10 KSI families, 97 evidence objects), the data schema for it,
and a signed 3PAO attestation letter from A-LIGN. Mirrored here under `conformance/`.
