# ServiceFlow Blog — Post Approval & Image Workflow

## How New Posts Work

Each new blog post goes through this 4-step process before it appears on the live site.

---

## Step 1 — Draft Delivered for Review

I'll send you a draft that includes:

| Field | What It Looks Like |
|-------|-------------------|
| **Slug** | `how-to-get-google-reviews` (URL-safe ID) |
| **Title** | The H1 headline for the post |
| **Category** | SEO & Google / Reviews / Automation / Websites / Business Growth |
| **Date** | Publication date |
| **Read time** | e.g. "5 min read" |
| **Excerpt** | 1–2 sentence teaser shown on the blog card |
| **Full body** | Complete article with H3 subheadings and tip boxes |
| **Image brief** | Description of what the image should show |

### Your response options:
- ✅ **Approved** — I add it to the site
- 🔄 **Edit X** — specific change, I revise and resend
- ❌ **Hold** — don't publish yet

---

## Step 2 — Sourcing the Image

Every post should have a real image. Three ways to get one:

### Option A — You supply it
Take or find a photo that matches the topic. Good sources:
- **Your own photos** — real client work photos always perform best for SEO and trust
- **Unsplash** (unsplash.com) — free, no attribution required
- **Pexels** (pexels.com) — free, no attribution required

**Image requirements:**
- Minimum 1200 × 630px (landscape ratio works best)
- JPG or WebP format
- File size under 500KB (compress at tinypng.com if needed)

### Option B — I find a stock image
Just say "find an image" and describe the vibe. I'll suggest 3 options from Unsplash and you pick one.

### Option C — Use the emoji placeholder
If no image is available yet, the post card and modal show a category emoji placeholder. You can add a real image later — just send it and I'll swap it in within 24 hours.

---

## Step 3 — Image Naming Convention

Name your image files using this format:
```
[post-slug]-hero.jpg
```

**Examples:**
- `map-pack-hero.jpg`
- `google-reviews-hero.jpg`
- `no-shows-automation-hero.jpg`

Upload to: **`/blog/images/[filename]`** on Vercel (add to the deploy folder)

---

## Step 4 — Adding the Post to the Site

Once you approve the draft and confirm the image:

1. I add the post object to the `P = { ... }` JavaScript object in `blog.html`
2. I add the card HTML to the `pgrid` div
3. If the post is the new Featured post, I update the `.feat` block
4. The `img` field in the post object is set to `/blog/images/[slug]-hero.jpg`
5. Deploy updated `blog.html` to Vercel

**Turnaround: same day if approved before 5pm.**

---

## Current Post Library

| Slug | Title | Has Image? |
|------|-------|-----------|
| `map-pack` | How to Get Into Google's Map Pack | ❌ Needs image |
| `reviews-text` | The Exact Text to Get 5-Star Reviews | ❌ Needs image |
| `no-shows` | Cut No-Shows by 80% With Reminders | ❌ Needs image |
| `website-cost` | How Much Should a Website Cost in 2026? | ❌ Needs image |
| `gbp-mistakes` | 10 GBP Mistakes Costing You Leads | ❌ Needs image |
| `booking-revenue` | How Booking Increased Revenue 30% | ❌ Needs image |
| `deposits` | Why You Should Collect a Deposit Upfront | ❌ Needs image |
| `local-seo` | Local SEO: The Complete Beginner's Playbook | ❌ Needs image |
| `referral` | Build a Referral Program That Sends You Clients | ❌ Needs image |

**Priority images to add first:**
1. `map-pack` — featured post, most visible
2. `reviews-text` — most popular post
3. `local-seo` — high traffic potential

---

## To Add a NEW Post

Send me:
1. Topic or working title
2. Target keyword (e.g. "how to get more google reviews")
3. Target audience (e.g. "hair salon owners", "HVAC contractors", "general service businesses")
4. Any specific tips, stats, or angles you want included

I'll write the full post, send it for review, and handle publishing once approved.

**Suggested next posts based on search volume:**
- "How to price your services" (high intent from business owners)
- "Best booking software for [trade]" series
- "How to get more calls from Google Maps"
- "SMS marketing for service businesses"
- "Before and after gallery: how to showcase your work"

---

## Quick Reference: Image Placeholder Swapout

To update an existing post's image after the site is deployed:

**In `blog.html`, find the post in the `P` object:**
```js
'map-pack': {
  cat: 'SEO & Google',
  img: '',    // ← CHANGE THIS to '/blog/images/map-pack-hero.jpg'
  ...
}
```

Change `img: ''` to `img: '/blog/images/map-pack-hero.jpg'`

The card and modal hero image will automatically show the real photo on the next deploy.
