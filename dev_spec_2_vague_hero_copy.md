# Vague hero copy — dev spec
Site: allbirds.com · Priority 2 · Urgent · Effort: Low (0.5-2 days)

## Problem
The hero headline and subhead are abstract and feature-led, failing to directly address the visitor's intent to find comfortable, sustainable shoes, which may cause them to bounce without engaging.

## Evidence (from the live site)
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN' and 'SHOP WOMEN' with no subheadline in the hero section.

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: No subheadline; the hero is a rotating carousel (based on body sample showing multiple 'NEW' products) and the copy is a brand slogan rather than a value proposition tied to visitor frustration.

## Required change
h1: Comfortable Shoes, Made from Nature; cta: Shop Best Sellers; notes: Add a subheadline: 'Free shipping & returns. Find your perfect fit in minutes.' This directly addresses the visitor's search for comfortable, sustainable footwear and provides a clear next step.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a subheadline: 'Free shipping & returns. Find your perfect fit in minutes.' This directly addresses the visitor's search for comfortable, sustainable footwear and provides a clear next step.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_vague_hero_copy` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
