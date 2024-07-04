---
title: Complex Catalog Queries
status: provisional
authors:
  - '@freben'
owners:
  - '@backstage/catalog-maintainers'
project-areas:
  - catalog
creation-date: 2024-07-02
---

<!--
**Note:** When your BEP is complete, all these pre-existing comments should be removed

When editing BEPs, aim for tightly-scoped, single-topic PRs to keep discussions focused. If you disagree with what is already in a document, open a new PR with suggested changes.
-->

# BEP: Complex Catalog Queries

<!-- Before merging the initial BEP PR, create a feature issue and update the below link. You can wait with this step until the BEP is ready to be merged. -->

[**Discussion Issue**](https://github.com/backstage/backstage/issues/NNNNN)

- [Summary](#summary)
- [Motivation](#motivation)
  - [Goals](#goals)
  - [Non-Goals](#non-goals)
- [Proposal](#proposal)
- [Design Details](#design-details)
- [Release Plan](#release-plan)
- [Dependencies](#dependencies)
- [Alternatives](#alternatives)

## Summary

<!--
The summary of the BEP is a few paragraphs long and give a high-level overview of the features to be implemented. It should be possible to read *only* the summary and understand what the BEP is proposing to accomplish and what impact it has for users.
-->

The catalog currently supports two query methods when listing entities: [the "filter" matcher](https://backstage.io/docs/features/software-catalog/software-catalog-api#filtering) which connects path-like keys with exact values, and [the "full text" matcher](https://backstage.io/docs/features/software-catalog/software-catalog-api#full-text-filtering) which can match on parts of multiple fields at a time. In particular the former is limited, very opaque and hard to learn, and has several shortcomings.

In response to recurring asks for support for richer and more complex queries, this BEP proposes a new extensible tree structured method (simply the "query" method below) that allows for clearer, more complex filtering to be performed.

## Motivation

<!--
This section is for explicitly listing the motivation, goals, and non-goals of
this BEP. Describe why the change is important and the benefits to users.
-->

### Goals

<!--
List the specific goals of the BEP. What is it trying to achieve? How will we
know that this has succeeded?
-->

- Queries can be written easily by hand, and can be understood by a human at a glance
- Support nested logical expressions, specifically the `AND`, `OR`, and `NOT` operators
- Keep supporting both the "filter" and the "full text" matchers, as parts of the (possibly nested) query
- Design the query format such that it can easily be extended with more operators and matchers in the future, without changing the overall syntax
- Design the query format such that it is user facing with TypeScript types and passed into e.g. the catalog client library by callers, as well as acting as the on-wire format sent to the catalog backend, without intermediate transformation

### Non-Goals

<!--
What is out of scope for this BEP? Listing non-goals helps to focus discussion
and make progress.
-->

- Inventing new matchers is not part of this BEP. Specifically, there have been asks for substring matching (for example by inserting percent signs in values as in SQL), and it is tempting to make more expressive matchers for example for relations. But those should be addressed in a separate BEP or feature request to avoid stalling this BEP on such design details.

## Proposal

<!--
This is where we get down to the specifics of what the proposal actually is.
This should have enough detail that reviewers can understand exactly what
you're proposing, but should not include things like API designs or
implementation.
-->

## Design Details

<!--
This section should contain enough information that the specifics of your
change are understandable. This may include API specs or even code snippets.
If there's any ambiguity about HOW your proposal will be implemented, this is the place to discuss them.
-->

## Release Plan

<!--
This section should describe the rollout process for any new features. It must take our version policies into account and plan for a phased rollout if this change affects any existing stable APIs.

If there is any particular feedback to be gathered during the rollout, this should be described here as well.
-->

## Dependencies

<!--
List any dependencies that this work has on other BEPs or features.
-->

## Alternatives

<!--
What other approaches did you consider, and why did you rule them out? These do
not need to be as detailed as the proposal, but should include enough
information to express the idea and why it was not acceptable.
-->
