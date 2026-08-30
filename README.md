# Brand Librarian

Brand Librarian is an open-source, evidence-aware asset retrieval engine for agents.
It helps an agent find candidate assets, explain the evidence behind each candidate,
surface uncertainty, and fail closed when the available evidence cannot support an
action.

This repository contains the reusable architecture, public schemas, validators,
tests, and a non-sensitive demonstration dataset. It does **not** contain the NUDE
brand archive or any private brand-library records.

## Repository role

- Public canonical source for the reusable Brand Librarian engine and its
  non-sensitive interoperability contract.
- Safe integration surface for consumers such as WebMCP tools and Reel Crew.
- Demonstration environment built from synthetic, public-domain, or explicitly
  approved assets only.

Before adding any file, read [REPO_BOUNDARY.md](REPO_BOUNDARY.md). All contributions
must satisfy [CONTRIBUTING.md](CONTRIBUTING.md).

## Current status

Governance scaffold only. No production engine, real archive metadata, or demo
dataset has been accepted yet.

## Trust model

Brand Librarian distinguishes:

- what is directly observable in an asset;
- what is inferred from a filename or path;
- what is asserted by an approved document;
- what is unknown or needs human review.

Visual similarity is not proof of product identity, colour availability, usage
rights, or suitability for a task. Consumers must not silently substitute an
unsupported asset.
