# Fintech Prototypes

Working prototypes by **Pia Rahman**, Senior Product Manager, built with [Claude](https://claude.ai).

**Live demo:** https://mpiarahman16.github.io/fintech-prototypes/

## 1. Voice Line Lab (`/voice-line-lab`)

A test lab for a card issuer's phone support (IVR) platform. Call the fictional Northpoint Bank in one of two ways:

- **Press 1 menu:** the traditional keypad tree.
- **Say it:** describe what you need in your own words, and the system detects the intent along with a confidence score.

What you can change and see:

- **Design choices:** how callers verify (approval in the bank's app, a texted one-time code, or security questions) and the confidence level below which the system confirms the intent before acting.
- **Real tasks:** lock a lost or stolen card, check the balance and due date, make a payment, or flag a charge you don't recognize.
- **Under the hood:** what the system heard, the detected intent and confidence, verification status, and the actions it took.
- **Agent screen on transfer:** a *warm* transfer passes the agent the intent, what the caller said and what's already been done, so the caller never repeats themselves. A *cold* transfer passes nothing.
- **Scorecard:** compares the two modes on caller turns, estimated call time, calls resolved without an agent, and warm vs. cold transfers. It's built only from calls made on the page.

## 2. What Late Invoices Cost You (`/late-invoice-calculator`)

A free tool for small B2B businesses, from the team behind Cash Collect IQ.

- **Your numbers in:** invoiced sales, payment terms, actual days to get paid, interest rate on credit used to cover gaps, write-off rate, and time spent chasing.
- **Annual cost out:** interest on cash tied up past terms, plus bad debt, plus chasing time, shown with the full calculation.
- **Get paid faster:** cash freed up and yearly savings from cutting days to get paid.
- **Reminder schedule:** a timeline fitted to your payment terms, from a heads-up before the due date to escalation.

## Run locally

No build step and no dependencies:

```bash
python3 -m http.server 8000
# visit http://localhost:8000
```

## Notes

- Concept work, not affiliated with any bank. Companies, customers, cards and transactions are invented.
- Intent detection in Voice Line Lab is keyword-based so the logic is visible. A production system would use a trained model with the same confidence-threshold behavior.
- The reference figure in the calculator comes from Xero Small Business Insights (US, Q2 2026). Every other number comes from the user's own inputs.
