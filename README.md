# VidCruiter (vidcruiter)

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

VidCruiter is a Moncton, Canada based recruitment technology company that provides a modular hiring platform - pre-recorded and live video interviewing, automated interview scheduling, skills and pre-employment testing, automated reference checking, audio interviews, and video proctoring.

**Access model: partner / enterprise gated.** VidCruiter does **not** publish a public, self-service developer API. There is no public developer portal, API reference, OpenAPI document, base URL, sandbox, or self-serve key issuance. This entry documents VidCruiter honestly as a gated integration provider rather than fabricating a public API surface.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vidcruiter/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vidcruiter/refs/heads/main/apis.yml)

## What is actually available

VidCruiter's programmatic surface is an integration capability, not an open API:

- **Pre-built connectors** to major ATS/HCM (Workday, Dayforce, ADP, Oracle, SAP SuccessFactors, Greenhouse, Lever, and 20+ others), background-check (Checkr, Certn, Turn.ai), calendar (Google, Office 365, Exchange, Outlook, iCloud), job boards (Indeed, Glassdoor, ZipRecruiter, Talroo, Seek), SSO (Okta, Google Workspace, Azure, SAML), and video conferencing (Zoom, Microsoft Teams, Google Meet, GoTo, Webex).
- **A bidirectional web-services integration.** In the documented Slate pattern, the ATS pushes application records to a per-tenant VidCruiter web-service endpoint (authenticated with a user token passed as a query string), and VidCruiter returns a `ShareableProfileUrl` for each completed interview via an API call, using a timestamp parameter so only new records are retrieved.
- **Account-provisioned endpoints.** An institution's unique API endpoint is obtained from a VidCruiter account representative. Endpoints are per-tenant; there is no public base URL.

## APIs (logical, honestly modeled)

The APIs listed in `apis.yml` are **logical resources marked `endpointsModeled: true`** - they describe what a VidCruiter integration would plausibly expose. No concrete paths, schemas, or base URLs were invented because none are published.

- **VidCruiter Partner Integration API** - the real, documented (but gated) web-services integration surface.
- **VidCruiter Candidates API** - modeled candidate/applicant records synchronized with an ATS/HRIS.
- **VidCruiter Interviews API** - modeled video/audio interview sessions and results.
- **VidCruiter Evaluations API** - modeled evaluator ratings, scorecards, and reference-check results.

## Pricing

Quote-based and gated behind a sales demo. VidCruiter publishes no official price list; third-party reviews cite a starting floor of roughly USD 5,000/year, with each module priced separately and integration fees billed on top. See [`plans/vidcruiter-plans-pricing.yml`](plans/vidcruiter-plans-pricing.yml). Figures there are indicative and third-party sourced, not official.

## WebSocket review

`review.yml` answers the standing question - **Does VidCruiter expose a documented public WebSocket API? No.** VidCruiter publishes no public API at all, so there is no server-push transport to model and no AsyncAPI document was authored.

## Tags

- Recruitment
- Video Interviewing
- Hiring
- HR Tech
- Applicant Tracking
- ATS Integration
- Candidate Screening
- Reference Checking

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/vidcruiter)
- [Website](https://vidcruiter.com)
- [Documentation](https://vidcruiter.com/integrations/)
- [Plans](plans/vidcruiter-plans-pricing.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
