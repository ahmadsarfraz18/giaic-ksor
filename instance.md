---
format: 2
name: giaic-ksor
title: GIAIC KSoR Sandbox
description: A minimal sandbox learning and practice record for testing KSoR mechanics, MCP tools, and document governance workflows.
toolchain:
  requires: ">=0.0.60"
  scaffolded: "0.0.60"
# `database.dsn_env` names the environment variable holding your Postgres DSN —
# never the DSN itself, which belongs in .env. It is filled in because naming a
# variable costs nothing and needs no database: `npm run dev` and `npm run build` do
# not read it, and the value only has to exist when you climb to the served
# rung. To climb: copy .env.example to .env and set KSOR_DB_URL, then
# `npm run provision` once (schema + grant), then `npm run refresh` to PUBLISH the
# record, then `npm run serve`. Serving does not publish — that is deliberate, and
# skipping refresh serves nothing.
# Nothing else here is required:
# `embedding:` already defaults to Gemini at 1536 dimensions, and leaving
# `retrieval:` out starts you with the abstention gate off and honest about it
# (turn it on afterwards with `ksor calibrate`, once the record is serving).
database:
  dsn_env: KSOR_DB_URL
# Where agents reach this record's MCP surface, and the semver it publishes as.
# Both go into /.well-known/mcp/server.json, the document an agent reads to
# DISCOVER this record instead of being told the URL. Leave mcp_url out until
# the server is actually published: an invented URL is worse than none.
# mcp_url: https://records.example.com/mcp
# version: 0.1.0
---

This record is authoritative for **the sandbox itself** — what this practice
record contains, how a document climbs the KSoR governance ladder within it,
and how the same governed knowledge is published to people and to agents. It
is a learning record: the corpus exists to exercise KSoR mechanics, the MCP
tools and the document governance workflows, nothing more.

Everything in `knowledge/` is a **sandbox sample** — practice technical notes
and practice policies written to test the mechanics. None of it is a real
company policy, a production codebase, or anyone's operating knowledge.

## What belongs here

Sample technical notes and practice policies, written or approved by the owner,
plus whatever else the mechanics need exercised. The audience is always
`public`.

## What does not belong here

- Production software codebases.
- Private credentials or secrets.
- Actual organization policies, or real business data.
- General trivia or broad world knowledge outside the sample test documents.

When an agent asks about any of those, the correct answer from this record is
**"not in this corpus"** — never a guess, and never something the agent reached
for from its own memory.

## Audience

`public` only. Every reader sees every document, and the site's static export
is governed the same way.

## Strictness

A question this record does not cover is declined, firmly — **"not in this
corpus"** is a correct answer, not a failure. Nothing here is loaded with
authority it was never given.
