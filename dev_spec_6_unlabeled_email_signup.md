# Unlabeled email signup — dev spec
Site: allbirds.com · Priority 6 · High · Effort: Low (0.5-2 days)

## Problem
The email signup form has an input with no visible label, relying solely on placeholder text, which can hurt accessibility and clarity.

## Evidence (from the live site)
> On homepage, forms array shows a form with n_inputs: 1, labels: [], submit: 'Sign Up'. Body sample includes 'Subscribe to our emails Sign Up'.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: Sign Up; notes: Email input lacks a visible label; only placeholder text is likely present.

## Required change
h1: Wildly Comfortable. Super Natural.; cta: Sign Up; notes: Add a visible label like 'Email address' and consider a clear value proposition (e.g., 'Get 10% off your first order').

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a visible label like 'Email address' and consider a clear value proposition (e.g., 'Get 10% off your first order').
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_unlabeled_email_signup` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
