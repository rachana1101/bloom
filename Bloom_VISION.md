# Bloom — Product Vision

*An AI garden designer that reads your plot and tells you what to plant.*

---

## The problem

Most people with a backyard plot, raised bed, or strip of bare soil don't know
what to do with it. They don't know how much sun it gets. They don't know which
direction it faces. They don't know which plants will thrive there in summer
versus winter. They walk into a nursery and pick whatever looks pretty, plant
it, and watch half of it die.

The information needed to plant well — light exposure, plot dimensions, soil
context, seasonal sun patterns — is *physically present* in their yard. They
just can't read it. Bloom reads it for them.

## The user

Anyone with a piece of real soil they can plant into:

- A raised bed in a backyard
- A patch of bare earth along a fence

The user leans toward the **beginner end** of the gardening spectrum — they
care about their space and want it to be beautiful, but they don't have deep
horticultural knowledge and don't want to spend hours researching. They have a
phone, they have a plot, and they want help.

Explicitly *not* for v1: container gardens, balcony pots, indoor plants,
hydroponics, full-property landscape design.

## The core moment

A user is standing in front of an empty or underperforming plot, phone in
hand, wondering *what should I plant here?*

They open Bloom. They take a photo (or a few photos across the day). Bloom
analyzes the plot, considers the season, and returns a simple visual planting
plan: 4–8 recommended plants placed in zones, with photos, plain-language
reasoning, and basic care notes.

That's the moment Bloom exists for.

## What Bloom does

**On-device computer vision** reads the plot:

- Plot dimensions and shape
- Orientation (which way is north?)
- Lighting and shadow patterns inferred from the photo(s)
- Existing vegetation (if any)
- Surrounding context (fences, walls, structures that affect light)

**An LLM layer** translates that understanding into recommendations:

- Considers the current season and how sun position will shift
- Picks plants from a curated database of beginner-friendly options
- Places plants in zones that match their light/depth needs
- Generates plain-language reasoning for each choice

**The output** is a simple visual plot card:

- A top-down view of the plot with plants placed in zones
- Each plant: photo, plain-language reason, basic care info
- A summer / winter toggle showing how the plan shifts with seasonal sun
- Designed to be screenshotted, shared, and taken to the nursery

## What's different about Bloom

Most garden-planning tools are either plant-ID apps (point at a leaf, get a
name) or generic planners (drag-and-drop a 2D template). Neither reads the
user's actual yard.

Bloom's wedge is **CV-driven plot understanding for someone who doesn't know
their own plot's conditions.** A beginner doesn't know if their bed gets "full
sun" or "partial shade." They don't know which corner faces north. They can't
estimate dimensions accurately. Bloom reads what they can't.

The seasonal-awareness layer compounds this: showing a beginner that the same
plot gets *different* light in summer versus winter is genuinely educational.
It's the moment they understand their own yard for the first time.

## Opinionated defaults (no preference toggles in v1)

Bloom v1 doesn't ask the user what they want. It picks for them, biased toward:

- **Beginner-friendly** — forgiving plants that are hard to kill
- **Beautiful** — aesthetics-first, color and form matter
- **Low-maintenance** — implicit in beginner-friendly
- **Non-toxic to pets** — silent fear most users won't think to mention
- **Pollinator-friendly when possible** — free win, pretty and good for bees

The user takes a photo. Bloom returns a plan. No questionnaire.

## v1 scope

**Geography:** Bay Area, USDA zones 9–10 only. The plant database is curated
for this zone. v1 will be excellent for one zone rather than mediocre for many.

**Plant types:** Vegetables just planting.

**Platform:** iOS, on-device CV via CoreML. One network call to the LLM for the
recommendation step.

**Output:** Top-down 2D plot card with placed plants, photos, and reasoning.
Summer / winter seasonal toggle.

**Persistence:** None in v1 — no accounts, no saved plots. Each session is
independent. The user screenshots or saves the plan if they want to keep it.

## Out of scope for v1 (deliberately)

- AR / 3D overlay (v2)
- Multi-plot or full-property management (v2)
- Watering schedules and care reminders
- Pest and disease diagnosis
- E-commerce / nursery integration
- User preference toggles — pollinator-only, native-only, low-water, etc. (v3)
- USDA zones outside 9–10 (v2)
- Vegetables (v3)
- "What's currently failing in my bed" mid-season mode (v2)
- Accounts, persistence, and notifications (v2)

## Roadmap

**v1 (Aug 30, 2026)** — The vision above. Demoable end-to-end on iPhone, on a
real Bay Area plot, with a real planting plan as output.

## Success criteria for v1

A non-gardener friend can:

1. Stand in their Bay Area backyard with an empty raised bed
2. Open Bloom on an iPhone
3. Take 1–3 photos of the bed
4. Get a planting plan they actually trust
5. Take a screenshot to the nursery and buy the plants on it
6. Plant them and have most of them survive

If that flow works, v1 is done.

---

*Bloom — design your garden, season by season.*
