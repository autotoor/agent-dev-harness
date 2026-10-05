# Shared Request Board

## Authority And Release

This document and recorded owner decisions govern the first release. This is a synthetic product, not existing software. The release includes viewing requests and editing their text and due date through a web interface and API. Users are authenticated current team members.

## Reading And Identity

Every current member, including the owner, can read every team request. Each request has a creator and one or more assignees. Shared identity means all views show the same saved request, not independent copies.

## Editing

A successful edit changes the shared request once and updates all views. Invalid text or invalid dates are rejected without mutation. A failed write preserves the previous version and indicates failure. The documents do not define which current members may edit a particular request. Unauthenticated and nonmember access is rejected.

## Work Sequence

The team can implement read-only lists, date rendering, and shared request storage separately from the edit controls and write endpoints. No production editing endpoint has been implemented.

## Release Boundary

Calendar export, external sharing, and membership administration are not part of this release. Their future design is not specified here.
