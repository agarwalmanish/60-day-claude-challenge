## Day 5: Context Engineering ##

### Prompt: Without Context ###

>
    Create a 30-day learning roadmap.
    
    Include:
    - Weekly milestones
    - Daily tasks
    - Resources
    - Projects
    - Final outcome
    
    Make it practical and beginner-friendly.
>

### Response ###
I'd be glad to build this out as a full roadmap with weekly milestones, daily tasks, resources, projects, and a final outcome. The one thing I need first: what's the subject?

A 30-day roadmap is shaped almost entirely by the topic — a plan for learning Python looks completely different from one for, say, sketching, Spanish, or system design. So tell me what you want to learn, plus two quick things if you have them in mind:

- **The topic** (e.g. Python, guitar, public speaking, data structures, watercolor, etc.)
- **Who it's for** — you, or someone else (this affects how "beginner-friendly" I pitch it)
- **Rough time per day** you can commit (30 min? 1 hour? 2+?)

Even just the topic is enough to get started — I can make reasonable assumptions on the rest and note them as I go. What are we learning?

### Prompt: With Context ###
>
    Create a 30-day learning roadmap.
    Context:
    - Current Situation: Professional
    - Current Skills: Web Fullstack Developer
    - Goal: AI Engineer
    - Available Time: 2-3 hrs
    - Experience Level: Intermediate
    - Preferred Learning Style: Videos, Projects and Reading
    Include:
    - Weekly milestones
    - Daily tasks
    - Resources
    - Projects
    - Final outcome
    Make it practical and beginner-friendly.
    Compare both outputs and identify:
    1. Which roadmap feels more personalized?
    2. Which roadmap would you actually follow?
    3. What role did context play in improving the result?
>

### Reponse: ###
I'll generate two versions of this roadmap — one **generic** (what a bare prompt produces) and one **personalized** (using everything you provided) — then compare them and answer your three questions. First, let me ground the resource recommendations in what's current, since AI tooling shifts fast.Let me find current, concrete resources (especially video-based, since that's a stated preference).I have what I need. Creating the deliverable now — a single file containing **both** roadmaps so you can compare them side by side and keep the one you'll actually use.Both roadmaps are in the file above. Here's the comparison you asked for.

**1. Which feels more personalized?**

Version B, by a wide margin — and the gap comes entirely from the context you supplied. Version A is a "learn AI from zero" template: it spends two of its four weeks re-teaching Python, math, and classical ML that you, as a working fullstack dev, either already know or don't need for this role. It would feel generic to you because it *is* generic — it was written for an imaginary average beginner. Version B starts from "you already build APIs, manage databases, and deploy to Vercel," so it skips straight to the AI application layer and even reuses your existing tools (pgvector on the Postgres/Supabase you know, the Vercel AI SDK in your React stack).

**2. Which would you actually follow?**

Version B — and not just because it's tailored. The deeper reason is that it matches your *actual goal*. The current consensus is that AI Engineering is an application-layer discipline: building chatbots, RAG pipelines, and agents on top of existing models rather than training them, and the combination of production engineering experience plus demonstrated LLM skills is one of the most competitive profiles in the 2026 market. Version A's deep-learning/CNN detour optimizes for an ML *researcher* path you didn't ask for. Version B also produces a shippable artifact every single week, which suits a busy professional who needs to see progress in 2–3 hour blocks — and it leans on the well-supported idea that you should build your first RAG pipeline without frameworks before layering in agents and evaluation, so you actually understand the abstractions instead of cargo-culting them.

**3. What role did context play?**

Each field you provided changed a specific decision, which is the whole point of the exercise:

- *Fullstack developer* → deleted ~14 days of redundant programming/web content and reframed function-calling as "typed API design you already do."
- *Intermediate + 2–3 hrs/day* → set the pace and a realistic ~70-hour total, with built-in light days.
- *Videos / projects / reading* → the resource mix is deliberately balanced (DeepLearning.AI and Scrimba for video, a build every week, docs for reading) rather than a wall of one format.
- *Goal: AI Engineer* → kept the focus on RAG/agents/production and cut model-training theory, because AI engineers build production software with AI at the core — it's not research or model training.
- *Professional* → made the capstone "add an AI feature to an app you already run," so all your effort goes to the new skill, not rebuilding scaffolding.

If you wanted to push personalization even further, the next lever would be pointing the capstone at one of your real products rather than a generic app — that's the difference between a roadmap that's *tailored to your category* and one tailored to *you specifically*. Want me to wire the plan to a concrete project you're already working on?

[AI Engineer 30 Day Roadmap PDF](AI-Engineer-30-Day-Roadmap.pdf)

### Key Learnings ###
**The bare prompt stalled.** When I asked for a "30-day learning roadmap" with no subject attached, Claude couldn't actually do anything useful. Its entire first reply was a polite *"what are we learning?"* plus a few follow-up questions. No deliverable, no value yet, just a request to fill the gap I'd left. 

The lesson landed harder than I expected: <ins>a vague prompt doesn't produce a vague answer, it often produces *no* answer, because the model has nothing concrete to act on</ins>. Either it stops to ask, or it guesses and gives you something generic.

**The context-rich prompt just ran.** The second time, the same instruction carried my situation (working professional), my background (fullstack web dev), my goal (AI engineer), my time budget (2–3 hrs/day), my level, and how I like to learn. Claude didn't ask a single question. It went and searched the web for resources, then built a roadmap shaped around *my* stack and schedule; even producing a generic version alongside the personalized one so the contrast was visible, and finishing with a share-ready carousel.

So my real takeaway is: **context isn't a "nice to have", it's what converts a prompt from a question into an instruction the model can execute.** The first version made Claude work *for* information; the second let Claude work *with* it. Same model, same words, wildly different leverage. Those six lines were the highest-return edit I could've made.