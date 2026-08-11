# Missing review count — dev spec
Site: allbirds.com · Priority 8 · High · Effort: Medium (2-5 days)

## Problem
The product page lacks a visible review count or rating summary near the price, which is a common trust signal that reduces purchase hesitation for new visitors.

## Evidence (from the live site)
> The page has a section 'Reviews for Anytime Ankle Sock' but no review count or star rating is visible in the provided inventory; the trust flags show 'reviews: true' but the count is not surfaced.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: The product page shows a 'Get Notified' CTA (likely for out-of-stock) and a reviews section, but no review count or rating is visible near the price.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart; notes: Add a review summary (e.g., '4.5 stars (1,200 reviews)') directly under the price to provide social proof and reduce hesitation.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a review summary (e.g., '4.5 stars (1,200 reviews)') directly under the price to provide social proof and reduce hesitation.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_missing_review_count` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
