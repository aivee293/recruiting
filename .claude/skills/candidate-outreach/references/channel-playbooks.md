# Channel Playbooks — Platform-Specific Outreach Guide

## LinkedIn InMail

### Specs

- **Subject line:** 200 characters max (but mobile cuts off at 30-40 characters — put hooks in first 30 chars)
- **Body:** ~1,900 characters max
- **Ideal length:** Under 400 characters (~50-70 words). LinkedIn data: InMails under 400 characters get **22% higher response rates** than longer ones.
- **Response rate benchmark:** 18-25% for recruiting (highest of any industry). Top performers hit 25-40%. Bottom: 2-5%. (SalesSo, LinkedIn, PostKing)
- **InMail credits:** Returned if candidate responds within 90 days
- **Mobile:** 57-70% of LinkedIn traffic is mobile — optimize for small screens

### Best Practices

- Subject line: specific, not clickbait. Reference their skill or a shared context.
- Open with personalization, not your company name
- Keep under 150 words — InMail response rates drop after ~500 characters
- End with a question, not a statement
- Use their first name, never "Dear [Full Name]"
- Send Tuesday-Thursday, 8-10am or 5-7pm their timezone
- Avoid InMails on Monday mornings (inbox flood) and Friday afternoons

### Common Mistakes

- Opening with "I came across your impressive profile"
- Pasting the entire JD in the body
- Including multiple CTAs ("apply here AND schedule a call AND check our careers page")
- Sending the same InMail to 50 people without personalization
- Using "We're disrupting..." or "Fast-paced environment..."

### GTM-Specific LinkedIn Notes

GTM professionals (sales, marketing, CS) live on LinkedIn differently than engineers:

- **They get MORE recruiter messages** — AEs and SDRs are heavily recruited. Your message competes with 10+ others per week.
- **They understand sales outreach** — They do it themselves daily. A lazy template is instantly recognized. Conversely, a great outreach message earns respect.
- **Lead with numbers** — GTM people think in metrics: ARR, deal size, OTE, quota attainment, team size, market opportunity. Be specific.
- **LinkedIn posts are gold** — GTM professionals post frequently about wins, lessons, frameworks. Reference their posts for strong personalization.
- **Comp is the elephant in the room** — Especially for sales, address OTE structure early or at least signal it's competitive. Vague comp messaging = ignored.
- **President's Club / awards** — If they've posted about hitting President's Club, quota attainment, or awards, reference it. It's their biggest pride.

### InMail vs. Connection Request Decision

**The data may surprise you:** Leonar (2026) found Connection Request + personalized note achieves **35-45% acceptance** with replies, while InMail averages **15-25% response**. Connection requests are free and often outperform paid InMails — but they measure different things (acceptance vs reply).

Use **InMail** when:

- You have clear personalization and a strong hook
- Candidate is senior (Director+) — they get fewer InMails
- You need to send a longer message (InMail allows ~1,900 chars vs 300 for connection note)
- You want a guaranteed inbox landing (no acceptance required)

Use **Connection Request + Note** when:

- You want to build a relationship before pitching (connect first, pitch in follow-up message 24-48hrs later)
- InMail credits are limited — connection requests are free
- Candidate is junior-mid level (connection requests feel less aggressive)
- You plan to nurture over time, not pitch immediately
- The candidate is in a less-saturated function (not engineering or sales — they get flooded)

**Advanced tactic — "Pattern Interrupt":** A blank connection request (no note) creates curiosity and sometimes outperforms a note for acceptance rate (20-30%). After they accept, send a substantive first message. Use sparingly and only when your profile clearly communicates who you are.

### SOBO (Send On Behalf Of) via InMail

If your hiring manager has LinkedIn Recruiter access, have them send the first InMail. Candidates are **2x more likely to respond to hiring managers** than recruiters. The recruiter can draft the message and the HM sends it with minimal effort. Reserve this for leadership hires and key ICs where response rates matter most.

---

## LinkedIn Connection Request

### Specs

- **Note:** 300 characters max (including spaces)
- **Without note:** Higher acceptance rate but no context
- **Acceptance rate:** 30-50% with personalized note, 20-30% without

### Best Practices

- 300 characters is brutal — lead with the hook, skip pleasantries
- Format: [Personalization]. [Why connecting]. [Soft CTA].
- After acceptance: wait 24-48 hours before sending a longer message
- Don't pitch in the connection request itself — just establish relevance
- Mention mutual connections if available (highest acceptance rates)

### Post-Acceptance Message

Once they accept, send a longer message (LinkedIn message, not InMail):

```text
Thanks for connecting, [NAME]! As mentioned, I'm with [COMPANY] and
we're [BRIEF]. I'd love to share more about what we're building —
would a 15-minute call work sometime this week?
```

---

## Cold Email

### Specs

- **Subject line:** 30-50 characters optimal (mobile preview). Personalized subject lines with tokens (name, company) measurably increase open rates.
- **Body:** 101-150 words for first touch (Gem sweet spot). Most recruiters send 170-210 words — shorter outperforms.
- **Response rate benchmark:** Recruiting email sequences average 21.3% reply rate / 7.9% interested rate (Gem, 4M emails). Personalized cold email: 15-23%. Generic: 5-10%.

### Finding Emails

- LinkedIn profile (some list email)
- GitHub profile (most developers have email visible or .patch trick)
- Personal website/blog contact page
- Conference speaker bios

### Deliverability

- Send from a personal email (<yourname@company.com>), not noreply@
- Avoid spam trigger words: "opportunity", "limited time", "act now"
- Don't include more than 2 links in cold outreach
- Plain text performs better than HTML for cold outreach
- Keep images minimal or none for first touch — images and GIFs can stand out but hurt deliverability early in sequences
- **Don't put compensation dollar amounts in cold emails** — specific salary figures can trigger spam filters (SourceWhale). Save comp details for responses and conversations.

### Deliverability Infrastructure

If doing volume outreach (20+ emails/day), set up proper infrastructure:

- **Separate outbound domain:** Use a subdomain (e.g., `talent.yourcompany.com`) or separate domain for cold outreach to protect your main company domain reputation
- **Warm up new mailboxes:** Send gradually increasing volumes over 2-3 weeks before running campaigns. Tools like Mailreach, Warmup Inbox, or built-in warmup in sequencing tools help.
- **Daily send limits:** Start at 10-15 emails per mailbox per day, increase gradually. Multiple mailboxes multiply capacity.
- **Monitor reputation:** Track bounce rates (keep under 3%), spam complaints, and deliverability scores weekly
- **Sender name:** "First Last" or "First from Company" outperforms "Company Recruiting" by ~27% open rate lift

### Subject Line Rules

- Lowercase or sentence case (not Title Case or ALL CAPS)
- No exclamation marks
- Specific > generic: "[Their project name] + [your company]" beats "Exciting opportunity"
- Question format works: "Quick question about [their domain]"
- Mutual connection in subject has highest open rates

### Best Practices

- Paragraph 1: Why you're emailing THEM (personalization)
- Paragraph 2: What makes this interesting for THEM (value prop)
- Paragraph 3: One-sentence CTA
- Sign with name + title + company (builds credibility)
- Reply to your own email for follow-ups (keeps thread context)

### Common Mistakes

- HTML-heavy templates that look like marketing
- Including the full JD as an attachment
- BCC mass sends (everyone knows)
- "If you're not the right person, please forward to..."
- Following up the next day ("just checking if you saw my email")

---

## GitHub

### Specs

- **No character limit** on issues/discussions
- **Style:** Technical, developer-authentic, never recruitery
- **Response rate:** Highly variable — high when genuinely relevant, zero if spammy

### Approach Strategies

**1. Issue/PR Comment (Highest Quality)**

- Find candidates through their contributions to relevant repos
- Leave a genuine technical comment first that come from a recruiter with no engineering background
- Follow up separately about the opportunity
- NEVER comment "great code, want a job?" on PRs

**2. Email from Profile**

- Many developers list email on their GitHub profile
- Reference specific repos, contributions, or code
- Show you actually looked at their work (mention specific files, approaches)

**3. Starring/Following First**

- Star their repos → they may check who you are
- Follow their profile → shows up in their notifications
- Then reach out via another channel

### GitHub-Specific Language

- Use technical terminology correctly
- Reference specific languages, frameworks, tools you saw in their repos
- Mention the specific repo or contribution that caught your eye
- Frame the role in terms of technical challenges, not HR-speak
- OK to ask about their open source work genuinely (not as a pitch setup)

### Absolute Don'ts

- Mass-opening issues titled "Job Opportunity!" on repos
- Copy-pasting the same message to multiple developers
- Confusing their personal projects with professional experience
- Getting technical details wrong (instant credibility loss)

---

## Twitter/X

### Specs

- **DM limit:** 10,000 characters (if they follow you or have open DMs)
- **Ideal DM length:** Under 280 characters for first touch
- **Reply limit:** 280 characters
- **Response rate:** 15-30% when done right (warm approach)

### Warm-Up Strategy (Recommended)

1. **Week 1:** Follow them, like 2-3 of their relevant tweets
2. **Week 1-2:** Reply to a tweet with a genuine, substantive comment (not "Great point!")
3. **Week 2:** Once there's some interaction, DM with context
4. This works because Twitter is relationship-native — cold DMs feel intrusive

### Direct DM (When Warm-Up Isn't Feasible)

- Keep it ultra-short and casual
- Reference a specific tweet or thread of theirs
- Don't use formal language — Twitter tone is conversational
- Include a light opt-out: "Totally cool if not your thing"

### Best Practices

- Match their communication style (emoji use, formality level)
- Don't DM people who primarily tweet personal content (not professional)
- Tech Twitter is great for engineers, data scientists, DevRel, and design
- GTM Twitter/X is active for sales leaders, founders, and marketing — search #SaaS, #B2BSales, #RevenueOperations, #DemandGen
- Less effective for mid-level individual contributors outside tech/GTM

### Common Mistakes

- Sending a LinkedIn-style formal message via Twitter DM
- DMing someone who clearly tweets about non-work topics only
- Using Twitter for executive outreach unless they're genuinely active there

---

## Reddit

### Specs

- **DM:** Available to all users unless disabled
- **Style:** Authentic, community-respectful, anti-corporate
- **Response rate:** Low if cold, moderate if you have community presence

### Golden Rule

Reddit users HATE unsolicited recruiter DMs. The approach must be community-first:

1. **Identify relevant subreddits** for the role (r/cscareerquestions, r/experienceddevs, r/MachineLearning, r/devops, etc.)
2. **Participate genuinely** for 1-2 weeks — answer questions, share insights, be helpful
3. **Build karma and credibility** in the community
4. **Then** DM select individuals whose posts/comments indicate relevant experience
5. **Always acknowledge** that recruiter DMs on Reddit are unusual

### Subreddit-Specific Norms

**Technical:**

- r/cscareerquestions: Career advice focus, some recruiting acceptable in threads
- r/experienceddevs: Senior engineers, recruiting DMs somewhat tolerated if very relevant
- r/MachineLearning: Research-heavy, reference papers and technical work
- r/devops, r/sysadmin: Practical focus, tool and infrastructure talk

**GTM / Business:**

- r/sales: Active community, open to career conversations, quota/comp discussions
- r/marketing: Broad marketing discussions, less tolerant of recruiting than r/sales
- r/startups: Founders and early GTM hires, good for startup roles
- r/CustomerSuccess: Growing community, CS-specific career discussions
- r/ProductManagement: PM career paths and job market talk

**General:**

- Role-specific subs for niche roles (r/UXDesign, r/analytics, etc.)

### What Works on Reddit

- Transparency about being a recruiter
- Self-deprecating humor about recruiting
- Genuinely useful contributions before any pitch
- Respecting "not interested" immediately

---

## Discord & Slack Communities

### Specs

- **DM availability:** Varies by server settings
- **Style:** Community-native, casual, helpful-first
- **Response rate:** High within active communities (30-50%+ if genuine member)

### Strategy

1. **Join relevant communities** (many tech communities are public or easy to join)
2. **Introduce yourself honestly** — many communities have #introductions channels
3. **Be helpful first** — answer questions, share resources, participate in discussions
4. **Build relationships** over 2-4 weeks
5. **Then DM selectively** — reference your community interactions

### Finding Communities

**Engineering:**

- Reactiflux, Python Discord, Gophers Slack, Kubernetes Slack, CNCF Slack

**Data/ML:**

- dbt Community Slack, MLOps Community, DataTalks.Club, Weights & Biases Discord

**Product/Design:**

- Lenny's Community Slack, Product School, Mind the Product
- Design Buddies, Figma Community, UX Collective

**Sales/Revenue:**

- Pavilion (formerly Revenue Collective) — curated, application-required, high-quality sales leaders
- RevGenius Slack — 35k+ revenue professionals, very active
- Modern Sales Pros — vetted community for sales leaders
- Sales Hacker Community — SDR through CRO-level discussions
- Bravado — sales community with rep-level engagement
- WomenInSales Slack — active network for women in sales/CS/revenue

**Marketing:**

- Exit Five — B2B marketing community (Dave Gerhardt), very active Slack
- Superpath — content marketing community, quality discussion
- Demand Curve — growth marketing community
- Product Marketing Alliance Slack — PMM-specific

**Customer Success:**

- Gain Grow Retain — CS leadership community
- The Customer Success Network Slack
- Success Hacker Community

**Industry-specific:**

- Fintech-specific Slacks, HealthTech communities, Climate Tech Slack

**Local:**

- City-specific tech/startup Slacks (e.g., NYC Tech Slack, Berlin Startups, London Tech)

### Community Outreach Etiquette

- Check community rules — many explicitly ban recruiting DMs
- If rules prohibit DMs, post in #jobs or #hiring channels instead
- Never mass-DM community members
- Be transparent about your role (recruiter/sourcer)
- Offer value even to people who aren't candidates (builds reputation)

### What Gets You Banned

- Joining and immediately DMing people
- Posting job ads in non-job channels
- Being dishonest about why you joined

---

## LinkedIn Voice Notes & Video Messages (GTM-Heavy)

### Specs

- **Voice note:** Up to 60 seconds, mobile only
- **Video:** Via LinkedIn native or Vidyard/Loom link
- **Response rate:** 2-3x higher than text InMail for GTM roles

### Why This Works for GTM

GTM professionals use voice and video in their own prospecting daily. A recruiter who sends a voice note or Loom speaks their language — it signals you understand their world.

### Best Practices

- **Voice notes:** Keep under 30 seconds. Introduce yourself, one sentence on why them, one CTA. Casual tone.
- **Video (Loom/Vidyard):** 60-90 seconds max. Show their LinkedIn profile or company website on screen while talking about why you reached out. Personal thumbnail matters.
- Send as a second touch (after text InMail), not as cold first touch
- Reference something specific — don't record a generic video you send to 50 people
- Name the video/note with their name: "Hey [NAME] — quick note about [COMPANY]"

### When NOT to Use

- Engineering roles (most engineers find voice/video outreach intrusive)
- Executive roles (feels too casual for VP+)
- Anyone who hasn't engaged with you at all (cold voice notes feel aggressive)

### Script Template (Voice Note)

```text
"Hey [NAME], it's [YOUR_NAME] from [COMPANY]. I sent you a note
earlier this week — wanted to put a voice to it. We're building
out our [TEAM] and your background at [THEIR_COMPANY] doing [WHAT]
really stood out. Would love 15 minutes to tell you more. Either
way, hope you're having a great week."
```

---

## GTM Events & Conferences

### Why Events Matter for GTM Sourcing

GTM professionals network aggressively at events — it's part of their job. Conference attendee and speaker lists are gold mines. Unlike engineers (who often avoid recruiter conversations at events), GTM people are open to career conversations at conferences.

### Key GTM Events

**Sales/Revenue:**

- SaaStr Annual / Europa — largest SaaS conference, heavy sales/CS/revenue attendance
- Dreamforce (Salesforce) — massive, good for enterprise sales profiles
- Pavilion events (CRO Summit, CMO Summit) — curated, high-quality executive crowd
- President's Club trips — company-specific, but award winners are top performers
- Gartner CSO & Sales Leaders Conference — enterprise sales leadership
- AA-ISP events — inside sales / SDR focused

**Marketing:**

- HubSpot INBOUND — massive marketing + sales conference
- Content Marketing World — content/demand gen marketers
- MozCon — SEO/growth marketing
- B2B Marketing Exchange — ABM, demand gen
- Demand Gen Report events — pipeline/revenue marketing

**Customer Success:**

- Gainsight Pulse — largest CS conference
- TSIA conferences — CS and services leadership

**Product:**

- ProductCon — product management
- Mind the Product — PM community events

### How to Source from Events

1. **Before:** Review speaker lists, attendee lists (if available), sponsor company exhibitor lists
2. **During:** Engage on event hashtags, comment on speaker posts, connect with attendees sharing content
3. **After:** Reference the event as a conversation starter: "Saw you were at [EVENT] — how was [SPEAKER]'s talk?"
4. Speaker lists are especially valuable — speakers are thought leaders and often top performers

### GTM Event Sourcing Message

```text
Subject: [EVENT_NAME] + [COMPANY]

Hi [NAME],

I saw you [SPOKE_AT / ATTENDED / WERE_MENTIONED_AT] [EVENT] —
[SPECIFIC_REFERENCE to their talk, panel, or post about the event].

We're building [TEAM] at [COMPANY] and your experience in
[THEIR_DOMAIN] is exactly what we're looking for. [ONE_DETAIL
about why this role is compelling for someone in their world].

Worth a quick chat?

[YOUR_NAME]
```

---

## GTM Podcasts, Newsletters & Content Platforms

### Why Content Channels Matter for GTM

GTM professionals consume a LOT of content — podcasts during commutes, newsletters for market intelligence, LinkedIn posts for thought leadership. People who appear as podcast guests, write newsletters, or post frequently are often top performers and thought leaders. These are both sourcing channels AND personalization signals.

### Key GTM Podcasts (Guest Lists = Candidate Lists)

- **30 Minutes to President's Club** — tactical sales, guest list is full of top AEs/managers
- **The Revenue Builders** (John McMahon & John Kaplan) — sales leadership
- **Pavilion Podcast / Revenue Vitals** — CRO/VP Sales level guests
- **SaaStr Podcast** — founders and GTM leaders
- **Lenny's Podcast** — product + growth, often features GTM leaders
- **Exit Five Podcast** — B2B marketing leadership
- **DGMG (Dave Gerhardt)** — B2B marketing, brand, demand gen
- **The Official SaaStr Podcast** — SaaS GTM strategy

### Key GTM Newsletters

- **The SaaStr Daily** — SaaS news and GTM strategy
- **Pavilion newsletters** — revenue leadership content
- **Lenny's Newsletter** — product-led growth, often GTM-adjacent
- **Kyle Poyar's Growth Unhinged** — PLG and pricing strategy
- **Exit Five Newsletter** — B2B marketing
- **RevGenius digest** — revenue community highlights

### How to Use for Outreach

1. **Podcast guests:** Search recent episode guest lists → high-quality candidates
2. **Newsletter authors:** People who write/curate newsletters are thought leaders in their function
3. **Personalization:** "I caught your episode on [PODCAST] about [TOPIC]" is an elite personalization signal
4. **Community engagement:** Subscribe, comment, share — build presence before outreach

---

## Referral Networks & Warm Intros (GTM Priority Channel)

### Why Warm Intros Are Critical for GTM

GTM professionals are inherently networked — their job IS relationships. They respond far better to warm intros than cold outreach. A referral from a respected peer carries 5-10x the weight of a cold InMail.

### GTM-Specific Referral Sources

- **Board members and investors** — Have wide GTM networks, carry credibility for VP+ roles
- **Current sales team** — Know who the top performers are at competitors
- **Customers** — Interact with sales/CS people daily at other companies
- **Channel partners** — Work with multiple sales orgs, know who performs
- **Former employees** — Especially those who left on good terms, now at target companies
- **Pavilion / community members** — Tight-knit, willing to make intros for the right opportunities

### Warm Intro Strategy

1. Map who in your org or network connects to the candidate
2. Ask for an honest assessment before the intro ("Is this person actually good?")
3. Make it easy — provide a forwardable blurb
4. Follow up quickly after the intro (within 24 hours)
5. Always close the loop with the referrer ("Thanks — we connected, great conversation")
