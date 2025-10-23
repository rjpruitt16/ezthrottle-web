# EZThrottle Marketing Site

The landing page and documentation for [EZThrottle](https://ezthrottle.network) - The World's First API Aqueduct.

---

## 🚀 What is EZThrottle?

Stop babysitting rate limits. Start living.

EZThrottle is distributed infrastructure built on BEAM that handles API rate limiting, multi-step workflows, and eventually consistent coordination - so you can close your laptop at 6pm and trust your infrastructure works.

**[Visit the site →](https://ezthrottle.network)**

---

## 📋 Trial Request Process

### How It Works

1. **Click "Request Trial"** on any paid tier (Starter/Growth/Pro)
2. **Your email client opens** with a pre-filled template
3. **Fill out the questions** (see template below)
4. **Send to support@ezthrottle.network**
5. **We review and respond within 24 hours**

### Why Email Templates?

We're building infrastructure that needs to be **reliable**. Manual trial approval helps us:
- ✅ Talk to every customer early
- ✅ Understand real use cases
- ✅ Learn which APIs people need
- ✅ Find the right customers to bet on
- ✅ Build relationships from day 1

**We're gambling on you. We want to know who we're betting on.**

---

## 📧 Trial Request Email Template

When you click "Request Trial", your email will be pre-filled with:

```
Subject: [Tier] Trial Request

Hi,

I'd like to request a trial of the [Tier] tier ([X] requests/month).

--- Please fill out ---

Who I am: 

Why I need EZThrottle: 

What APIs I'm rate limited on: 

How I'll use [X] requests to evaluate: 

I understand EZThrottle is immature but powerful - I'll use it carefully: Yes

Thanks!
```

### What We're Looking For

**Good Requests (We'll Approve):**
- Clear pain point with rate limiting
- Specific APIs you're working with
- Concrete evaluation plan
- Understanding this is beta software

**We'll Redirect to Free Tier:**
- No clear use case yet
- Just want to "try it out"
- No evaluation plan
- Vague about APIs

**No judgment either way - just helps us support the right people at the right time.**

---

## 🎯 Who Should Request a Trial?

### Perfect for You If:
- You're hitting 429 errors regularly
- You've written exponential backoff code you hate
- You need to coordinate multi-step workflows
- You want to process data in the background
- You value infrastructure that "just works"

### Not Ready Yet If:
- You've never hit a rate limit
- Just curious about the tech
- Need real-time synchronous responses (<5 sec)
- Require enterprise SLAs today

---

## 💡 What Makes EZThrottle Different?

### 1. **Smart Routing**
SDK only sends rate-limited requests (429s) to EZThrottle. Everything else goes direct. You're not proxying all traffic - just overflow.

### 2. **Distributed Coordination**
2 req/sec per machine × 1000 machines = 2,000 coordinated req/sec to APIs. Proper distribution, not abuse.

### 3. **Curated Rate Limits**
We maintain safe defaults. Need higher rate for your API? Send us docs, we'll verify and add it to global config. Everyone benefits.

### 4. **Built on BEAM**
WhatsApp handled 2B users with 50 engineers on BEAM. Discord scales to millions on Elixir. Proven tech for 40 years.

### 5. **Solo Founder**
Direct access to the person building it. No support tickets disappearing into the void.

---

## 🏗️ The Roadmap

**Phase 1: Today**
- Reliable rate limiting
- Webhook delivery
- Smart SDK routing

**Phase 2: 2026**
- Static workflows (define steps explicitly)
- Multi-step coordination
- Long-running tasks

**Phase 3: Future**
- Dynamic workflows (define goal, not steps)
- Agent-driven coordination
- "Do this work and give me the answer"

---

## 🛠️ Tech Stack

- **Frontend:** Static HTML + Tailwind CSS
- **Backend:** Gleam (BEAM/OTP)
- **Infrastructure:** Fly.io edge network
- **Philosophy:** Boring tech that lasts

---

## 📁 Repo Structure

```
ezthrottle-web/
├── index.html          # Main landing page
├── faq.html           # Comprehensive FAQ
├── vercel.json        # Routing config
└── README.md          # This file
```

---

## 🚢 Deployment

This is a static site deployed on Vercel with rewrites to TrackTags for auth.

Routes:
- `/` → Main landing page
- `/faq` → FAQ page
- `/signup` → TrackTags signup flow
- `/login` → TrackTags login flow
- `/workspace` → TrackTags workspace

---

## 🤝 Contributing

See a typo? Have a suggestion? Found a better way to explain something?

**Pull requests welcome!**

This is marketing copy - if you can make it clearer, simpler, or more honest, please do.

---

## 📞 Contact

**Email:** support@ezthrottle.network  
**Founder:** [Rahmi Pruitt](https://www.linkedin.com/in/rahmi-pruitt-a1bb4a127/)  
**YouTube:** [@theblacktechexperience](https://www.youtube.com/@theblacktechexperience)

---

## 📜 License

Marketing content: Do whatever you want with it.

If you're building something similar and this copy helps - great! Just don't pretend to be EZThrottle.

---

## 💭 Philosophy

> "Infrastructure should be boring. It should work while you live your life."

We're building the aqueduct for the internet. Roman aqueducts lasted 2,000 years. BEAM has lasted 40 years. EZThrottle is built to last.

**Not for hype. For reliability.**

---

**Ready to try it?**

[Sign up for free](https://ezthrottle.network/signup) (10k requests/month)  
or  
[Request a trial](mailto:support@ezthrottle.network?subject=Trial%20Request) (Starter/Growth/Pro tiers)

🏛️
