# Shift — User Guide

Shift is your AI cofounder. You tell it an idea; it researches, writes a plain-English spec, breaks the work into phases, and then hands off to the coding team (CAE) to actually build it.

This guide assumes zero coding experience. If a word appears that you don't recognize, Shift explains it on first use. You can always ask "what does X mean?" in the middle of a conversation and Shift will answer.

---

## What Shift does

1. **Takes your idea** — you describe what you want, in plain English
2. **Researches** — figures out the best tools for the job and what accounts you'll need
3. **Writes a product spec** — a plain-English document that says what we're building and who for
4. **Writes a build plan** — breaks the work into 3-6 phases, each one shippable
5. **Builds phase 1** — hands off to CAE's coding agents; Forge writes code, Sentinel reviews it
6. **Shows you what was built** — you try it, tell Shift what's missing or broken
7. **Keeps going** — next phase, next phase, until you've got what you wanted

You can stop at any step. Type `shift resume` later to pick up where you left off.

---

## Starting your first project

Open a terminal (on Mac: press `cmd+space`, type "terminal", hit enter). Then type:

```
shift new my-first-project
```

Replace `my-first-project` with whatever you want to call it (letters, numbers, dashes — no spaces).

Shift will ask you three questions. Answer in your own words; don't stress about sounding technical.

**Question 1:** What are you building?
> One or two sentences. Example: "A website where people can upload a recipe and get back a grocery list."

**Question 2:** Who is it for?
> One sentence. Example: "People who cook at home but hate writing shopping lists."

**Question 3:** Is this a website, a phone app, a chat bot, or something else?
> Shift usually guesses right from your first answer. Just say "yes" if it's right.

After those three, Shift starts researching. Takes about a minute.

---

## What you'll see

### After research
Shift tells you (in plain English) what tools it'll use and what accounts you'll need to create. Example:

> I'll build this as a website using Next.js (that's a tool for making websites that run fast) and store recipes in a Postgres database (that's the most common type of database). You'll need accounts with:
>
> - **Supabase** — stores your data. Free to start.
> - **Vercel** — where your site lives so people can visit it. Free to start.
>
> Sound good?

You approve (or tell it to change something), then it moves on.

### After the PRD (product spec)
Shift shows you a plain-English summary of what it's going to build. Example bullet points:

- A user can paste or upload a recipe
- The system extracts the ingredients
- The user sees a grocery list they can print or email to themselves
- Users can save recipes to a library under their account

You approve (or ask for changes).

### After the roadmap
Shift shows you the phased plan. Example:

- **Phase 1 — Recipe paste:** user can paste text, see extracted ingredients
- **Phase 2 — Recipe saving:** user can log in, save recipes, see library
- **Phase 3 — Grocery list:** generate and print a grocery list
- **Phase 4 — Email / share:** email lists to self, share URLs

Approving kicks off phase 1. It runs in the background for 15-60 minutes depending on complexity.

### While it's building
You can close the terminal and go do something else. Run `shift status` anytime to see progress:

```
=== my-first-project — Shift status ===
  Phase: execute
  Currently: building phase 1 (running)
  Next: wait for phase 1 to finish, then try it out
```

### When a phase finishes
Shift tells you what was built, gives you a command to try it, and waits for feedback.

---

## Commands you'll use

| Command | What it does |
|---------|-------------|
| `shift new <name>` | Start a new project |
| `shift resume` | Pick up where you left off |
| `shift next` | Do the next step |
| `shift status` | See done / in-progress / blocked / next |
| `shift help` | Context-aware help — offers three concrete options to get unstuck |
| `shift learn <topic>` | Explain a concept in plain English |

Topics you can ask `shift learn` about: `cae`, `forge`, `sentinel`, `scout`, `arch`, `herald`, `phase`, `tmux`, `env-vars`

---

## When things go wrong

Shift doesn't blame you or dump error messages. When something fails, you'll see:

> That didn't work — probably a network hiccup. Nothing was destroyed; your idea and answers are saved. Three options:
>
> 1. Retry (I'd try this first)
> 2. Skip ahead with a default and fix it later
> 3. Take a break and come back; run `shift resume`

Pick one. If you're confused, run `shift help` — it reads the current state and offers options.

---

## Keeping secrets safe

When your project needs API keys (for sending emails, logging in users, etc.), Shift walks you through creating them one at a time. Each key gets saved in a file called `.env` that stays on your machine — never on GitHub.

You'll see Shift ask things like:

> To send emails when users sign up, we need a Resend account. Free for the first 3,000 emails per month. Here's what to do:
>
> 1. Go to https://resend.com
> 2. Create an account
> 3. Find Settings → API Keys
> 4. Click Create API Key, name it "shift-my-project"
> 5. Copy the key (starts with `re_`) and paste it here

You paste, Shift saves it, never shows it back.

---

## What Shift v3.0 does NOT do yet

- **Deploy your site live** — v3.0 stops at "code is version-controlled in GitHub." Deploying to a live URL is coming in a later release.
- **Custom domains / DNS** — same as above.
- **Team collaboration** — one user per project for now.
- **Payments / subscriptions (Stripe)** — planned.
- **Auto-migrate between interfaces** — v3.0 is terminal-only. Telegram (v3.1) and web (v3.2) are coming.

If you hit a limit, Shift tells you and offers a manual workaround.

---

## The short version

1. `shift new my-project`
2. Answer three questions
3. Approve the PRD
4. Approve the roadmap
5. Wait for phases to build, try them, give feedback
6. Ship when done

You don't need to know anything else.
