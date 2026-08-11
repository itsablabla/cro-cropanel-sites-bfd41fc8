# Out-of-stock notification form — dev spec
Site: allbirds.com · Priority 7 · High · Effort: Medium (2-5 days)

## Problem
The product page for Anytime Ankle Sock shows a 'Get Notified' CTA, indicating the item is out of stock, but the form likely only captures an email without offering alternatives or a clear restock timeline, risking lost sales.

## Evidence (from the live site)
> CTA 'Get Notified' present on product page; no add-to-cart button visible in crawl data.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: Out-of-stock item with email capture for restock notification; no alternative suggestions or expected restock date.

## Required change
h1: Anytime Ankle Sock; cta: Get Notified; notes: Add a restock date or 'Join Waitlist' with size selection, and suggest similar in-stock socks to retain purchase intent.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a restock date or 'Join Waitlist' with size selection, and suggest similar in-stock socks to retain purchase intent.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_out_of_stock_notification_form` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
