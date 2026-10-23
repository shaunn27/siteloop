# SiteLoop

SiteLoop is an offline-first internal marketplace for reusing construction
materials across project sites. Before a new purchase order is raised, each
request is checked against compatible surplus held by other sites. The app
follows the material from the initial match through approval, dispatch, and
verified receipt, so reuse is counted only when the receiving site accepts the
material.

## Why SiteLoop

Construction projects often have usable materials left over while another
project is buying the same or an equivalent item. SiteLoop makes that
opportunity visible within a project portfolio and records enough operational
detail to answer:

- Is the surplus technically compatible with the request?
- Is it available before the receiving site needs it?
- Has it been approved and inspected before dispatch?
- How much actually arrived in usable condition?
- Is reuse still worthwhile after handling, haulage, and inspection costs?

## Core workflows

### 1. Create and match a request

A requester describes the material needed, quantity, site, and required date.
The reuse check compares the request against listed and forecast surplus using
the material's specification fields rather than a simple product name. Match
results explain why a candidate is eligible or rejected, including hard
specification gates such as:

- Material type and dimensions
- Grade or condition
- Colour and finish
- Strength or performance requirements
- Lead time and availability

Forecast surplus is shown as a possible future source but cannot be reserved
until the source site counts and lists it.

### 2. List and manage surplus

Source sites can list available or forecast surplus with its quantity,
condition, specifications, photos, notes, confirmation date, and expiry. Stock
can be held while a transfer is being arranged, helping prevent the same
material from being promised to multiple requests.

### 3. Approve and transfer

An eligible match moves through approval before it can be dispatched. The
transfer records the source and receiving sites, quantity, delivery order,
vehicle/haul information, inspection details, and transfer costs. SiteLoop
also estimates whether the proposed movement is financially worthwhile after
handling, inspection, disposal, and haul costs.

### 4. Dispatch and verify receipt

Dispatch is recorded by the source site manager after the required approvals.
The receiving site then records the delivered and accepted quantities, delivery
order number, inspection result, condition, and rejection reason. The app
separates:

- Quantity dispatched
- Quantity delivered
- Quantity accepted on site
- Quantity rejected or damaged

This prevents rejected material from being counted as successful reuse.

### 5. Field operations and offline use

The field experience supports site crews working from a phone, including
dispatch/receipt actions, site inspections, photos, and QR-code scanning.
App data is persisted in the browser and the service worker caches the web
application for offline use. Camera scanning requires the deployed site to be
served over HTTPS; a code can also be entered manually.

## Current pilot scope

The bundled prototype includes examples for:

- Concrete interlocking pavers
- Precast concrete kerbs
- Porcelain floor tiles

Structural materials such as reinforcement bar are intentionally outside the
pilot scope. Reusing structural materials requires engineering approval,
certificates, and traceability controls that this prototype does not provide.

## Reporting and decision support

The application includes portfolio views for request stages, surplus,
transfers, accepted quantities, avoided purchases, disposal avoided, and
material-flow outcomes. It can also show illustrative carbon estimates for
eligible concrete items and provides CSV copy/export actions for reporting.

Cost and carbon figures are decision-support estimates, not verified
financial or environmental claims. The source contains reporting references
and assumptions so these values can be reviewed before being used in formal
project reporting.

## Repository structure

- `siteloop-web/` — deployable prebuilt web application.
  - `index.html` — application entry point.
  - `assets/` — compiled JavaScript and CSS bundles, including QR scanning.
  - `icons/` — PWA icons.
  - `manifest.webmanifest` — installable web-app metadata.
  - `sw.js` — offline cache and network handling.
- `siteloop-offline.html` — standalone single-file offline build.
- `vercel.json` — static hosting configuration for the `siteloop-web/`
  directory.

## Project status

SiteLoop is a working prototype for validating construction-material reuse
workflows. It uses seeded demonstration data and browser-local persistence;
it does not currently provide a shared backend, authentication, multi-user
synchronisation, or integration with procurement and enterprise systems.
