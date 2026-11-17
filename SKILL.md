---
name: captions-engine
description: Writes Meta headlines, primary text and short descriptions from the on-image headline, body and the offer's ICP in a Google Sheet ad-copy list. Use when someone types /captions-engine or shares an ad-copy sheet.
---

# /captions-engine

Turns ad copy (on-image headline + body rows in a Google Sheet) into three Meta text fields per ad: **Meta headline**, **primary text** and **description**, with one final and one alternative of each. The rules are generic. They adapt to each row's hook type, and the offer facts, ICP and target age are collected fresh every run.

## Core idea (why this works)
Each Meta ad has five text surfaces, each read at a different moment:

| Surface | Where | Reader's state | Job |
|---|---|---|---|
| On-image headline (hook) | On image, large | Still scrolling | Stop the scroll |
| Body | On image, small | Just stopped | Say what the fix is |
| Primary text | Above image | Interested, deciding | Answer the next question in their head |
| Meta headline | Below image, next to CTA | About to tap | The next step to take, in a few words |
| Description | Under the Meta headline (not shown on every placement) | Glancing before tapping | One supporting fact that lowers the risk |

Primary text is read after the hook has already worked, so it must never repeat the hook or the body. It adds new information on the same angle.

## Step 1: Intake
1. Get the Google Sheet link. Read it with the Google Sheets tools (get_spreadsheet for tabs, get_values for rows).
2. Map the columns: ID, angle/group, on-image headline (hook), body, existing Meta headline, existing primary text, existing description, CTA. The on-image headline and body are required. If a Meta headline or description column is missing, the skill creates it. If any column is unclear, ask. Don't guess.
3. Confirm scope: which tab, and all rows or a subset.

## Step 2: Context questions (every run)
First pull what's already known from memory and project context: offer name, price, guarantee, delivery time, ICP, target age, landing page / CTA destination, banned claims.

Then ask 2-4 multiple-choice questions for anything missing or that might have changed. These two are **required every run**, even if memory has an answer (confirm it):

1. **What's the offer's name?**
   - Options: the offer names already on file, plus "Other (type it)"
2. **What age range are these ads targeting?**
   - 25-34
   - 35-44
   - 45-60
   - 60+
   - Mixed / broad (type the range)

Other typical questions, asked only when needed:
- Which ICP this offer targets (who they are, their main pain, the words they use, whether they own the decision)
- Offer facts to confirm (price, guarantee terms, timeline, what's included)
- Destination and CTA (landing page, lead form, Messenger, call booking)
- Claims that need sign-off or are off-limits

**How age changes the writing:**

| Age range | Writing adjustments |
|---|---|
| 25-34 | Can be a bit quicker in rhythm. Still plain, still no slang or hype |
| 35-44 | Plain and direct. Lead with time and money saved |
| 45-60 | Simplest wording, no technical terms, slightly calmer pace. Lead with safety, trust and reputation |
| 60+ | Same as 45-60, plus shorter sentences and very explicit next steps |

Then make a **Confirmed facts** list and an **ICP snapshot** (offer name, who, age range, pain, their words, decision-maker yes/no). Only confirmed facts go into the copy. Anything unconfirmed gets flagged, never written in as true.

## Step 3: Classify each row's hook type

| Hook type | Example signal | Primary text job | Meta headline job |
|---|---|---|---|
| Pain / problem question | "Still stuck on...?" | Name the cost of staying stuck, then show the way out | The next step out of the problem |
| Fear / risk | "Worried your...?" | Make the risk concrete and calm, then show how it's removed | The safe next step |
| Desire / outcome | "Get X in Y days" | Show what has to happen to get there, and what they hand over vs get back | The step that gets the outcome |
| Identity callout | "Property managers:..." | Show you get their world (their tasks, their words) | Who it's for + what to do |
| Offer / guarantee | "$X or it's free" | Explain why the guarantee is safe to believe and what qualifies | Start, with the risk removed |
| Proof / number | "500+ hours found" | Where the number comes from, and what it means for them | The number as a benefit |
| Curiosity | "The one task..." | Pay off the curiosity fast in line 1, then the offer | The payoff |
| Objection | "No dev team needed" | Answer the next objection after this one | The removed barrier |

If a row mixes types, use the one the hook leads with. If it doesn't fit any type, say so and write to the closest one.

## Step 4: Write the Meta headline (final + alternative)
Every row gets a Meta headline, even if the sheet didn't have one. Build it from three inputs:
1. **On-image headline (hook):** keep the same angle, never copy its wording.
2. **Body:** pull the concrete promise the body makes (outcome, price, timeline, guarantee). Don't add a promise the body doesn't make.
3. **ICP:** use the ICP's own words for their problem or result (e.g. "your app", "your business", "your customers").

Rules:
- Write it as the **next step the reader takes**, in **5-6 words max**, starting with an action verb. It can work as a short summary of the whole offer.
  - Good: "Secure Your App, Then Launch It", "Fix the Gaps Before You Launch", "Finish Your App and Go Live"
- **Mature, not clever.** No wordplay, no punchy taglines. Generic is fine if it reads clean.
- Don't name the call or the team ("Talk to us", "Get expert help", "Book a check"). The CTA button already asks for the call.
- Stay under 40 characters (it gets cut on mobile past that).
- If the row already has a Meta headline that passes these checks, keep it as the final. Say so, and still give an alternative.
- The alternative uses a different lever (e.g. final = action, alt = risk reversal or ICP callout). Label which lever.

## Step 5: Write the primary text (final + alternative)
Structure:
1. **Line 1 (first ~125 characters)** has to work on its own, because that's all that shows before "See more". It speaks directly to the ICP's situation (e.g. a business owner with an almost-finished app). It's new information, not the hook reworded.
2. **Middle (2-4 short lines):** why acting is in their own interest, what happens, what they hand over vs get back, and what risk is removed. Use only confirmed facts, written for the ICP's situation.
3. **Price and guarantee** go in the middle, never in line 1. If the body already states the price or guarantee, leave the dollar figure out or word the guarantee differently.
4. **Last line:** a clear next step that matches the CTA button and the destination.

Style rules:
- **Mature, not clever.** A layman should understand it in one read.
- Talk to the reader as "you". Name who it's for when that helps (e.g. "If you run a small business...").
- Short lines with blank lines between them. No dense paragraphs.
- Never repeat sentences from the hook **or** the body.
- No em dashes. No hype words (revolutionary, game-changing, unlock). Plain English.
- No invented claims, numbers, testimonials, add-ons or terms. Avoid "most people..." claims you can't back up. Use "many".
- Keep the same angle as the row's hook and body.
- Match the wording to the target age range (Step 2 table).
- Aim for 60-150 words.

The **alternative** takes a different route on the same angle (e.g. final leads with the cost of waiting, alt leads with the risk reversal). Label what changed.

## Step 6: Write the description (final + alternative)
A short line that sits under the Meta headline. It doesn't show on every placement, so the ad must work without it.

Rules:
- **Short:** 3-6 words, under 30 characters.
- One supporting fact from the Confirmed facts list: the guarantee, the timeline, the price, or what's included.
  - Good: "Money back if it's late", "Fixed price. No surprises.", "Live on your own domain"
- Don't repeat the Meta headline or the hook. It adds something they don't say.
- Mature, not clever. No CTA wording (the button does that).
- The alternative uses a different fact. Label which one.

## Step 7: Self-check every row before showing it
- [ ] Offer name and target age were confirmed this run
- [ ] Line 1 is new info, speaks to the ICP and works without "See more"
- [ ] No repeated hook or body wording in the primary text, Meta headline or description
- [ ] Price and guarantee are not in line 1
- [ ] Every claim is on the Confirmed facts list
- [ ] Mature, not clever. No em dashes, no hype, written to "you"
- [ ] Wording fits the target age range
- [ ] Line breaks are in
- [ ] Meta headline is 5-6 words max, under 40 characters, an action, and doesn't name the call or team
- [ ] Description is under 30 characters and adds a different fact
- [ ] Last line matches the CTA and destination

Fix anything that fails before output. Show only the refined version.

## Step 8: Output
1. The ICP snapshot (with offer name and age range), the confirmed facts used, and any flags (claims needing sign-off).
2. A table per row: ID | Hook type | On-image headline | Body | Meta headline (final / alt) | Primary text (final / alt) | Description (final / alt) | Why it works (one line)
3. A short "How to do this yourself" note: the hook type spotted, and the one move that made each field work.
4. End with **What to do next**.

## Step 9: Write back
- Don't write to the sheet until the user says so. If their request already says to add the copy into the cells, that counts as confirmation.
- Prefer a working tab (e.g. "Draft - Claude") over the Final tab. Never overwrite existing copy unless asked, and keep the previous version available so it can be reverted on request.
- Column order when creating new columns: ID | On-image headline | Body | Meta headline (final) | Meta headline (alt) | Primary text (final) | Primary text (alt) | Description (final) | Description (alt) | CTA.
- State the exact tab and range before writing, then write in one pass.
- Afterwards, read the range back to check that nothing shifted.
