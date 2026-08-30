# Public Repository Boundary Contract

Status: binding governance contract for this repository.

## Purpose

This public repository makes the Brand Librarian method inspectable and reusable
without publishing any private archive. It is an engine and contract repository,
not a mirror, catalogue, or export of the NUDE collection.

## Canonical truth

- This repository is canonical for the public engine, public schema contract,
  validators, public tests, and approved demo fixtures.
- The private `nude-brand-library` repository is canonical for NUDE-specific
  inventory records, provenance, evidence, governance decisions, and internal
  selection policy.
- The external source archive is canonical for source asset bytes. Neither Git
  repository owns or replaces those source files.
- Public examples are illustrative. They never establish facts about the private
  NUDE archive.

## Content allowed in public

- Reusable source code and configuration with no secrets or private endpoints.
- Generic schemas and validators that reveal no private records.
- Synthetic, public-domain, or explicitly release-approved demo assets.
- Redacted fixtures created specifically for public tests.
- Architecture, threat model, usage documentation, and integration contracts.
- Aggregate statistics only when separately approved for public disclosure.

## Content prohibited in public

The following must never be committed, included in release artifacts, written to
CI logs, bundled into browser code, or returned by a public endpoint:

- Original NUDE images, videos, audio, documents, or derivatives such as crops,
  thumbnails, contact sheets, embeddings, or perceptual hashes.
- The complete or partial real inventory, filenames, directory layout, local
  absolute paths, symlink targets, asset IDs, content hashes, or stable mappings
  that reveal private holdings.
- Private metadata, annotations, product bindings, rights status, provenance
  records, evidence packets, review notes, internal selection policy, or
  `needs_review` queues.
- Secrets, API keys, tokens, credentials, private URLs, account identifiers,
  environment dumps, request logs, or private endpoints.
- Model transcripts, prompts, traces, caches, or generated reports containing any
  prohibited value above.

Renaming, truncating, hashing, encoding, compressing, or moving prohibited data
does not make it public-safe.

## Source asset rule

Source assets are external, read-only inputs. The engine may receive an authorized
reference at runtime, but it must not modify, rename, move, delete, normalize,
transcode, or write metadata into the source file. Generated previews and caches
must live outside the source archive and outside version control.

## Provenance and evidence

Every non-demo metadata claim must carry an explicit basis such as:

- `visual_observation`
- `filename_or_path_inference`
- `approved_document`
- `human_confirmation`
- `unknown`
- `needs_review`

`human_confirmation` must identify the scope and authorized role of the confirmer.
It confirms only the stated field; it does not establish ownership, publication
rights, legal clearance, product identity, or another field unless the confirmer
has that authority and the evidence record says so explicitly.

Inference must not be promoted to confirmed fact. Similarity must not establish
identity, rights, product variant, or fitness for use. Missing evidence must fail
closed rather than trigger silent substitution.

## Public integration contract

Consumers may ask for task-relevant candidates and bounded explanations. Public
interfaces must return only the minimum fields required for the task. They must
not provide bulk export, archive enumeration, private paths, source hashes, or
private evidence chains.

## Release gate

Before every public push or release, scan the staged tree and built artifacts for:

1. absolute and home-directory paths;
2. source filenames and archive directory names;
3. hashes or IDs copied from the private inventory;
4. image, video, audio, document, archive, database, and model-weight binaries;
5. credentials, environment values, private URLs, logs, prompts, and traces;
6. private metadata and governance notes;
7. source maps or browser bundles containing excluded material.

Any uncertain file is rejected until reviewed. Public-safe status must be based on
the staged bytes, not on the filename or author intent.

## Changes to this contract

Changes require explicit owner review. A consumer integration, demo deadline, or
model request cannot weaken this boundary implicitly.
