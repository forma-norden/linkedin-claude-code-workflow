# LinkedIn Ad Campaign Builder

> **Best for:** teams that want campaign creation to happen from one configuration sheet instead of manual work inside LinkedIn's UI.

## Why this workflow matters

LinkedIn campaign manager is built for one-campaign-at-a-time work.

Claude Code replaces the UI with a repeatable build pattern: a Google Sheet holds the campaign configuration, then Claude Code reads it and creates the campaigns through the API.

## The Google Sheet structure

| Column | What to put here |
| --- | --- |
| Campaign Group | Parent group name |
| Campaign Name | Your naming convention |
| Targeting Type | `ABM List` / `Broad ICP` / `Retargeting` |
| Audience | Audience name from your saved audience library |
| Ad Folder | Path to creative assets in Google Drive |
| CTA | Button text and destination URL |
| Budget | Daily budget |
| Start Date | Launch date |

## Building the skill

Prompt:

> "I want to create LinkedIn ad campaigns via the LinkedIn Marketing API. Help me set up authentication, then build a skill that reads a Google Sheet and creates a campaign with targeting and at least one ad creative. Save as `.claude/skills/linkedin-ads.md`."

Claude Code will iterate through authentication errors and request structure until it produces a working script. Once it works, checkpoint it.

## Running it

Once the skill exists, campaign creation becomes a single prompt:

> "Read my campaign config sheet [link] and create all campaigns marked `Ready to Launch`. Confirm before executing."

Claude Code should summarize what it is about to create before it writes anything.

## Scaling to Meta and Google

The same campaign-config-sheet pattern can be reused across Meta and Google once those connectors exist in your stack.

That means one operating model, even when multiple ad platforms are involved.

## Ad copy generation

Use [Copy Framework Template](10%20Copy%20Framework%20Template.md) before campaign creation so the copy and targeting stay aligned.

Prompt:

> "Using my copy-framework.md file, write three ad headline and body copy variations for the ABM targeting campaign. Persona is [title] at [company type]. Tone: direct, no fluff."

Copy review should remain human. The campaign creation workflow should stay automated.

## Where to go next

If the campaign builder is in place, connect it back into [The Signal Loop](05%20The%20Signal%20Loop.md) so the same account lists feed both outbound and retargeting.
