# VidCruiter (vidcruiter)

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
