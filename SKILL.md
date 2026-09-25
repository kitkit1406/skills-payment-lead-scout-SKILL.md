---
name: telegram-payment-lead-scout
description: Scan approved Telegram business/payment groups for legitimate prospective clients who are actively looking for payment processing, PSPs, acquiring, bank accounts, vIBANs, APMs, payouts, or related fintech services.
---

# Telegram Payment Lead Scout

## Purpose

Find legitimate prospective clients in approved Telegram groups by identifying posts that show clear commercial intent for payment, banking, acquiring, PSP, fintech, or merchant services.

This skill is for business lead discovery only.

Do not collect or surface leads whose posts are clearly about stolen cards, forged documents, hacked accounts, money laundering, fraud proceeds, account takeovers, or other criminal services.

## What Counts as a Potential Lead

Treat a post as a potential lead when it indicates that the person or company is actively looking for one or more of the following:

- PSP
- payment gateway
- card processing
- acquiring
- MID / dedicated MID
- merchant account
- payment processor
- business bank account
- vIBAN / IBAN
- SEPA / SWIFT
- local payment methods
- APMs
- payouts
- collections
- settlements
- open banking
- banking rails
- local bank transfer solutions
- cross-border payments
- high-risk processing
- forex / CFD payment processing
- iGaming payment processing
- crypto-fiat payment rails
- e-commerce payment processing
- recurring billing
- chargeback-friendly acquiring
- multi-currency processing
- Apple Pay / Google Pay acceptance
- local CAD / GBP / EUR account capability
- Canada Interac
- PIX
- Nequi
- PromptPay
- other local payment methods

## High-Intent Phrases

Flag messages containing language such as:

- looking for PSP
- need a PSP
- looking for payment provider
- need payment provider
- looking for payment gateway
- need payment gateway
- looking for card processing
- need card processing
- looking for acquiring
- need acquiring
- need acquirer
- looking for acquirer
- looking for MID
- need MID
- dedicated MID needed
- looking for merchant account
- need merchant account
- looking for business bank account
- need business bank account
- looking for IBAN
- looking for vIBAN
- need IBAN
- need vIBAN
- looking for SEPA
- need SEPA
- looking for SWIFT
- need SWIFT
- looking for banking solution
- need banking solution
- looking for payment solution
- need payment solution
- looking for payment rails
- need payment rails
- looking for local payment methods
- need local payment methods
- looking for APM
- looking for APMs
- need APM
- need APMs
- looking for payout solution
- need payout solution
- looking for collection solution
- need collection solution
- looking for settlement solution
- need settlement solution
- looking for open banking
- need open banking
- looking for bank transfer solution
- need bank transfer solution
- looking for local transfer solution
- need local transfer solution
- looking for cross-border payment solution
- need cross-border payment solution
- looking for high-risk PSP
- need high-risk PSP
- looking for forex PSP
- need forex PSP
- looking for CFD PSP
- need CFD PSP
- looking for iGaming PSP
- need iGaming PSP
- looking for ecommerce PSP
- need ecommerce PSP
- looking for crypto payment provider
- need crypto payment provider
- looking for multi-currency account
- need multi-currency account
- looking for Apple Pay processing
- looking for Google Pay processing
- need Interac
- looking for Interac
- need PIX
- looking for PIX
- need Nequi
- looking for Nequi
- need PromptPay
- looking for PromptPay

## Intent Variations

Also detect informal or abbreviated language such as:

- any PSP?
- any provider?
- any acquirer?
- any gateway?
- who can provide PSP?
- who can offer processing?
- who has acquiring?
- who has MID?
- who can onboard?
- who can support [GEO]?
- who can process [business type]?
- any solution for [GEO]?
- any payment solution for [business type]?
- provider needed
- processor needed
- gateway needed
- acquiring needed
- banking needed
- IBAN needed
- vIBAN needed
- MID needed
- PSP needed
- urgent PSP
- urgent MID
- urgent gateway
- need provider ASAP
- need solution ASAP
- searching for provider
- searching for PSP
- searching for gateway
- seeking PSP
- seeking payment provider
- seeking acquirer
- require PSP
- require gateway
- require acquiring
- require merchant account

## Commercial Detail Signals

Increase confidence when the post also includes one or more of:

- monthly volume
- turnover
- expected volume
- processing volume
- average ticket
- average transaction
- GEO
- country list
- currencies
- settlement frequency
- payout frequency
- chargeback ratio
- MCC
- business vertical
- forex
- CFD
- iGaming
- e-commerce
- subscription
- crypto
- licensed / regulated
- website
- company name
- KYB
- KYC
- incorporation country
- card brands
- Visa / Mastercard
- local APMs
- SEPA
- SWIFT
- ACH
- Faster Payments
- Interac
- PIX
- Nequi
- PromptPay

## Lead Scoring

Score each candidate:

### Hot
Clear active buying intent plus commercial details.

Examples:
- "Need a PSP for forex, EU GEOs, €1.5M monthly volume."
- "Looking for dedicated MID for UK traffic, 300k monthly."

### Warm
Clear need but missing important details.

Examples:
- "Looking for payment gateway for high-risk."
- "Need business account with SEPA and SWIFT."

### Possible
Weak or ambiguous commercial intent.

Examples:
- "Any PSP here?"
- "Who works with forex?"

Do not classify normal provider advertising as a client lead unless the poster is clearly asking for a solution.

## Exclusions

Do not surface posts that are clearly seeking or offering:

- stolen cards
- cloned cards
- carding
- CC dumps
- CVV data
- forged documents
- fake IDs
- hacked accounts
- mule accounts
- stolen bank accounts
- fraud proceeds
- laundering services
- cash-out services for criminal funds
- account takeovers
- unauthorized access
- scam infrastructure

Also ignore:
- obvious spam
- pure provider advertisements
- job posts
- unrelated crypto speculation
- general market discussion with no buying intent
- old posts when a recent-only scan is requested

## Group-Level Rule

Do not reject an otherwise legitimate payments or fintech group because one member posted suspicious content.

Assess individual posts.

However, if the group itself is clearly a criminal marketplace, do not mine it for leads.

## Output Format

For every potential legitimate client, record:

- Telegram display name
- Telegram username if visible
- Group name
- Date / time
- Exact intent summary
- What they need
- GEO
- Business type
- Monthly volume
- Payment methods
- Banking rails
- Settlement requirements
- Website if stated
- Lead score: Hot / Warm / Possible
- Missing information
- Suggested next response

Do not invent missing information.

## Suggested Response Drafting

When asked to draft a reply, keep it short and commercial.

Example:

"Hi, I saw you're looking for a PSP for forex. We may have options depending on GEO and volume. Can you send your website, monthly volume, target countries, and required payment methods?"

Do not promise approval.

Use:
- subject to provider review
- subject to KYB
- depends on GEO and business profile

## Workflow

When the user asks to scan approved groups:

1. Open each approved group.
2. Review recent messages for buying-intent language.
3. Identify legitimate payment-related needs.
4. Ignore provider ads unless they are also requesting a solution.
5. Exclude criminal or clearly fraudulent requests.
6. Record each candidate lead.
7. Avoid duplicates when the same person repeats the same request.
8. Produce one final lead table.
9. Do not message anyone unless the user has separately approved outreach.

## Search Concepts

Look for semantic intent, not just exact keywords.

Examples of intent:
- seeking
- looking for
- need
- require
- searching for
- anyone has
- who can provide
- who can offer
- any solution
- any provider
- urgent
- ASAP
- recommendations
- introduction needed
- connect me with
- can anyone help with

Combine these with payment concepts:
- PSP
- acquiring
- MID
- gateway
- processing
- merchant account
- bank account
- IBAN
- vIBAN
- SEPA
- SWIFT
- APM
- payouts
- settlements
- transfers
- open banking
- local payments
- card processing
- merchant services

The goal is to identify genuine commercial buying intent, not simply keyword matches.
