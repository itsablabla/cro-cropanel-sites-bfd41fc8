# Free shipping threshold hidden — dev spec
Site: allbirds.com · Priority 4 · High · Effort: Medium (2-5 days)

## Problem
The homepage hero promotes 'Free ground shipping on orders over $100' but the threshold is not visible on the hero or in the main navigation, creating an expectation gap for users who may not see the fine print.

## Evidence (from the live site)
> Homepage body_sample: 'Free ground shipping on orders over $100' appears in the top bar, but the hero section (H1: 'Wildly Comfortable. Super Natural.') and CTAs ('SHOP MEN', 'SHOP WOMEN') do not mention the threshold. The threshold is only in the site-wide announcement bar, which may be overlooked.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: Free shipping threshold is only in the announcement bar, not in the hero or near CTAs.

## Required change
h1: Wildly Comfortable. Super Natural. Free Shipping Over $100; cta: SHOP MEN / SHOP WOMEN; notes: Include the free shipping threshold in the hero or near CTAs to set clear expectations.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Include the free shipping threshold in the hero or near CTAs to set clear expectations.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_free_shipping_threshold_hidden` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
