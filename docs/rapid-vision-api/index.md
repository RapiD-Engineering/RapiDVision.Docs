# RapiD Vision API

The RapiD Vision API is a RESTful API that lets partner systems (typically an ERP) read and, in a couple of cases, update RapiD Vision data. Most data fetching happens automatically through the RapiD Vision and RapiD Vision Explorer applications — this API is for direct, external integration.

## External API Surface

This is the subset of the API published for external partners. It currently covers three resources:

- [Order](order.md)
- [OrderRule](orderrule.md)
- [Batch](batch.md)

Products, analytics, and most update/delete operations are internal only and aren't part of this external surface.

## Authentication

Every request needs either:

- A Bearer token (`Authorization: Bearer {token}`) — an Azure AD access token, or
- An API key (`X-Api-Key: {key}`) — issued for your company by RapiD Engineering.

Your account or key must be linked to a valid company registered with RapiD Engineering.
