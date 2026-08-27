# Willow Dental Care — AI Receptionist Demo

A live, working demo of an AI front-desk assistant for dental practices. Built to show small clinics
what an always-on receptionist looks like — answering hours/insurance questions and starting the
booking flow, 24/7.

**Live demo:** [willow-dental-ai-receptionist.vercel.app](https://willow-dental-ai-receptionist.vercel.app)

## What it does
- Answers patient FAQs (hours, insurance, services) grounded in the clinic's real info
- Walks patients through booking (name, preferred time, reason for visit)
- Runs entirely client-side — talks directly to Claude via the Anthropic API

## Stack
Vanilla HTML/CSS/JS · Anthropic Messages API (`claude-sonnet-4-6`)

## Why
Most small clinics lose after-hours calls to voicemail. This demo shows a low-cost way to
capture those questions instantly instead.

## Security considerations
- API key lives server-side only (Vercel environment variable), never exposed to the browser.
- The agent cannot diagnose, prescribe, or make clinical claims — enforced in the system prompt and verified in testing.
- Tested against prompt injection attempts (see EVALUATION.md); the agent stays in its receptionist role.
- Booking requests are logged, not auto-confirmed — a human always makes the final call.

## Evaluation
10/10 manual test cases passed, covering FAQ accuracy, booking flow, medical-scope refusal,
and prompt injection resistance. Full test set and results in [EVALUATION.md](./EVALUATION.md).
