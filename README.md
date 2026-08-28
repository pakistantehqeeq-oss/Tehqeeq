# Tehqeeq | تحقیق

Open source media verification infrastructure for Pakistan.

---

## Why this exists

Every time something happens in Pakistan... AJK, Balochistan,
an election, a crackdown... the same thing follows. Videos
everywhere. Nobody can tell what's real. Both sides push
their version. Confusion wins by default because confusion
is easy and verification is hard.

But there's a deeper problem underneath that.

When you ask an AI what actually happened in some event,
the answer is usually "not documented, cannot verify." Not
because the truth doesn't exist. Because the only people
who bothered to document it had a reason to. And people
with a reason to document things have a reason to frame
them a certain way.

Unbiased people don't document because nobody built them
the infrastructure to do it easily and safely.

Tehqeeq is that infrastructure.

---

## What we're building

One flow. User pastes a link. Two things happen.

**Layer 1... the metadata trail**

Where has this video or image appeared before? When was
the first appearance? What was it labeled then? Where did
it spread and in what order?

No verdict. Just the trail. User sees "this video appeared
on Dawn in 2024 labeled as something else" and draws their
own conclusion.

Under the hood this chains four open source tools:

yt-dlp pulls the video and description from any platform
including Instagram, which no AI can currently access
directly.

Whisper transcribes the audio... handles Urdu, English,
and mixed code switching.

Keyframe extraction pulls representative frames and throws
them simultaneously at Google Reverse Image, Yandex Images,
InVID and the Wayback Machine archive.

Results get aggregated into a single timeline. First
appearance, subsequent appearances, label changes, spread
pattern. All of it visible. None of it interpreted.

**Layer 2... the framing anatomy**

What is actually being claimed. Why people think it's bad,
steelmanned. Why people think it's good, steelmanned.
What's verifiable and what's missing context.

This layer uses AI... but not AI we host. After the metadata
report is generated, one button opens your AI of choice
with everything preloaded. Your account, your API, no black
box on our side.

The prompt is published openly. No proprietary analysis.
No verdict. Just structure that lets you think clearly
about real content with wrong framing... which is the
actual problem more often than fake content.

We publish the prompt because we have nothing to hide about
how the analysis works. If the prompt is wrong, tell us.
We'll fix it publicly.

---

## The problem this solves

Crowd intelligence already catches fake content pretty well.
Someone always comments "this is from 2019." The harder
problem is real content with wrong framing. The BYD post
is real. The AJK video is real. The framing around them
is what breaks.

Tehqeeq handles both... metadata catches the fake, framing
anatomy handles the real but misleading.

---

## What we're not building

A verdict engine. We will never tell you something is good
or bad. The moment we do that we become another biased
voice and the infrastructure becomes useless.

Raw information. No verdicts. You decide.

---

## The documentation layer

Parallel to the verification tool, we're building a versioned
anonymously contributed record of Pakistani political events,
institutional claims and documented patterns.

Think Wikipedia meets Reddit meets git history, built for
Pakistani context with real anonymity protection and
verified/unverified/contested tiers.

When the verification tool finds that a video first appeared
in 2023 labeled as something specific, that finding feeds
into the documentation layer permanently. Future searches
pull from it automatically. The database gets smarter with
every case.

---

## Architecture

User pastes link
↓
yt-dlp fetches content and metadata
↓
Whisper transcribes audio to text
↓
Keyframe extraction hits reverse search APIs simultaneously
(Google Reverse Image, Yandex, InVID, Wayback Machine)
↓
Metadata report generated... timeline, appearances, labels
↓
"Analyze framing" opens AI with everything preloaded
↓
Findings feed into documentation layer


All open source. No proprietary dependencies. Costs
roughly $10-20 a month to run at phase one scale.

---

## Why open source and distributed

Because single owner infrastructure can be pressured,
shut down, or compromised. We've seen it happen.

Tehqeeq is built from day one with no single point of
failure. Multiple maintainers, mirrored repositories,
no central server anyone can switch off with a phone call.

The findings belong to everyone. The infrastructure
belongs to no one.

---

## Current status

Problem defined. Architecture clear. Looking for first
contributors to start building the pipeline.

yt-dlp integration is the logical starting point.
If you want to pick it up, open an issue.

---

## How to contribute

Pakistani and Indian contributors both welcome. Same
broken information environment, different sides of it.

Developer... open an issue, pick something, build it.
The pipeline has four distinct components any of which
can be built independently.

Researcher... the documentation layer needs people who
will write one verified entry about one event they
witnessed or can source. One entry is enough.

Designer... the tool needs a UI that works on mobile
in Pakistan on slow connections.

Journalist... your methodology input shapes how the
framing anatomy prompt works. That matters more than
code.

Discord: https://discord.gg/m4sjuKQzn

---

## How we work

Same standard for state and non-state actors. A fake
video is a fake video regardless of who benefits from
it spreading. A misleading frame is a misleading frame
regardless of which side uses it.

Methodology is public. Prompt is public. Edit history
is public. If anything we do is wrong, tell us with
evidence and we'll fix it visibly.

---

## Mantra

Verify. Contextualize. Distribute.

---

*No government affiliation. No political party. No
corporate funding. Maintained by contributors who think
accurate information is infrastructure, not a luxury.*

*"Today, the poet is also indebted to the soil...
there is blood in the pen, not ink."*
*... Ahmed Faraz*
