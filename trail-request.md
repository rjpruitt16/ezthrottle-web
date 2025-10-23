# Trial Request Email Template System

## Overview

Users clicking "Request Trial" on Starter/Growth/Pro tiers will open their email client with a pre-filled template. This creates a human-first qualification process.

---

## Email Template Structure

### Subject Line:
`[Tier] Trial Request` (e.g., "Pro Tier Trial Request")

### Body Template:
```
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

---

## The Questions (Purpose)

### 1. "Who I am"
**Purpose:** Context on user type (indie hacker, startup, enterprise)
**Why it matters:** Helps you prioritize and tailor support level

### 2. "Why I need EZThrottle"
**Purpose:** Understand pain severity
**Filters:** People with real pain vs tire-kickers

### 3. "What APIs I'm rate limited on"
**Purpose:** Know which APIs they're using
**Why it matters:** 
- You can verify rate limits
- Add to curated config if needed
- Spot patterns (everyone uses OpenAI)

### 4. "How I'll use [X] requests to evaluate"
**Purpose:** Understanding evaluation plan
**Filters:** Serious users have a plan, tire-kickers don't

### 5. "I understand EZThrottle is immature but powerful - I'll use it carefully"
**Purpose:** Set expectations + liability waiver
**Why it matters:** They're acknowledging beta status

---

## What Happens When You Receive Email

### Step 1: Read the Request
- Who are they?
- Is this a good fit?
- Do they have real pain?

### Step 2: Respond Within 24 Hours
**If approved:**
```
Hey [Name],

Thanks for reaching out! I'm approving your trial request.

Here's what happens next:
1. Sign up at ezthrottle.network/signup (use same email)
2. I'll manually upgrade you to [Tier] for 30 days
3. You'll get [X] requests/month to evaluate
4. Email me anytime: support@ezthrottle.network

A few things to know:
- EZThrottle is in beta - there may be rough edges
- If you hit issues, email me immediately
- I'm monitoring closely and will help debug

Looking forward to seeing how it works for you!

Best,
Rahmi
```

**If not approved (gently redirect):**
```
Hey [Name],

Thanks for your interest!

Based on what you described, I think the Free tier (10k requests/month) 
might be a better starting point. It'll let you:
- Test the integration
- Verify it solves your problem
- See if you need the higher tier

Try it out: ezthrottle.network/signup

If you exhaust 10k quickly and need more, reply back and 
I'll reconsider upgrading you.

Best,
Rahmi
```

### Step 3: Track in Spreadsheet
Simple CSV/Google Sheet:
- Email
- Tier Requested
- Date Requested
- Approved? (Y/N)
- Trial Start Date
- Trial End Date
- Converted? (Y/N)
- Notes

---

## Why This Approach Works

### 1. Human Touch
Not automated signup → you talk to every customer early

### 2. Qualification
Bad fits self-filter (too much friction for tire-kickers)

### 3. Expectation Setting
They acknowledge beta status in writing

### 4. Data Collection
You learn about use cases, APIs, pain levels

### 5. Relationship Building
Every trial customer knows you personally

---

## Sample Real Emails You Might Get

### Good Request (Approve):
```
Who I am: Founder of a B2B SaaS product

Why I need EZThrottle: We scrape competitor websites for pricing 
intelligence but keep hitting rate limits. Currently spending 10+ 
hours/week babysitting retries.

What APIs I'm rate limited on: Scraperapi.com, OpenAI for analysis

How I'll use 500k requests to evaluate: Run our pricing intelligence 
pipeline for 2 weeks with real customer data. Need ~20k requests/day.

I understand EZThrottle is immature but powerful - I'll use it carefully: Yes
```

**Your response:** APPROVED ✅
**Why:** Real pain, clear use case, serious evaluation plan

---

### Weak Request (Redirect to Free):
```
Who I am: Student

Why I need EZThrottle: Want to try it for my school project

What APIs I'm rate limited on: Not sure yet

How I'll use 2M requests to evaluate: Will see

I understand EZThrottle is immature but powerful - I'll use it carefully: Yes
```

**Your response:** Redirect to Free tier
**Why:** Not serious, no clear plan, likely won't use 2M

---

### Interesting Request (Approve + Ask Questions):
```
Who I am: AI researcher at university

Why I need EZThrottle: Building a dataset from Reddit API for research 
on online communities. Need 500k+ comments for analysis.

What APIs I'm rate limited on: Reddit API (60 req/min limit)

How I'll use 2M requests to evaluate: Fetch 500k comments over 2 weeks, 
process through sentiment analysis. Will publish results in paper.

I understand EZThrottle is immature but powerful - I'll use it carefully: Yes
```

**Your response:** APPROVED + offer to help
**Why:** Interesting use case, potential case study, academic credibility

---

## Rate Limit Config Process

When user mentions API you don't have config for:

### Step 1: Research
- Look up official API docs
- Find rate limit specs
- Check if it's 2 req/sec or higher

### Step 2: Add to Curated Config
```gleam
// In your config.gleam
pub fn get_rate_limit(domain: String) -> Float {
  case domain {
    "api.openai.com" -> 3.0  // 3 req/sec (verified safe)
    "api.anthropic.com" -> 2.0  // 2 req/sec (conservative)
    "api.reddit.com" -> 1.0  // 60 req/min = 1 req/sec
    _ -> 2.0  // Safe default
  }
}
```

### Step 3: Tell User
```
FYI: I've added reddit.com to our curated config at 1 req/sec 
(their 60 req/min limit). This will apply to all EZThrottle users.
```

---

## Scaling This Process

### Now (Manual):
- You read every email
- Approve manually
- Personal relationship with each trial user

### Later (Semi-Automated):
- Auto-approve if certain criteria met
- Still review all requests
- Flag interesting ones for personal outreach

### Much Later (Automated):
- Self-serve trials up to Growth tier
- Manual review only for Pro+
- You focus on enterprise customers

**But for now: Keep it manual. First 100 customers = your foundation.**

---

## What Success Looks Like

### Week 1 After Launch:
- 5-10 trial requests
- 2-3 approved
- 1-2 interesting conversations

### Month 1:
- 50+ trial requests
- 20+ approved
- 5+ converted to paid
- 2-3 case study candidates

### Month 3:
- 200+ trial requests
- 80+ approved
- 30+ paying customers
- 10+ testimonials

---

## The Real Win

**You're not just selling software.**

**You're having conversations with potential customers BEFORE they use the product.**

This means:
- You understand their pain deeply
- You can shape features based on their needs
- They feel heard and supported
- They become evangelists

**This is your moat. BigCos can't do this at scale.**

---

## Files Updated

### index.html (ezthrottle-complete.html)
- Starter tier button → mailto link with template
- Growth tier button → mailto link with template  
- Pro tier button → mailto link with template
- Free tier → still goes to /signup (self-serve)
- Enterprise → still "Contact Sales"

### The mailto URLs are URL-encoded with newlines (%0A)

When clicked, opens email client with:
- To: support@ezthrottle.network
- Subject: [Tier] Trial Request
- Body: Pre-filled template ready to fill out

---

## Next Steps

1. ✅ Deploy updated index.html with mailto links
2. ✅ Monitor support@ezthrottle.network inbox
3. ✅ Create simple tracking spreadsheet
4. ✅ Prepare response templates (approved/redirect)
5. ✅ Document rate limits as you learn them

---

**This is your sales process. Simple, human, effective.**
