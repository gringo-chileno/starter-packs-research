# Fediverse Starter Packs: Prototype Session Handoff

## What this is

Research page for the ActivityPub WordPress plugin team's Lisbon 2026 meetup project. Curated WordPress blog recommendations organized into starter packs that users can follow on the fediverse via ActivityPub.

**Live research page:** https://gringo-chileno.github.io/starter-packs-research/
**GitHub repo:** https://github.com/gringo-chileno/starter-packs-research
**Linear projects:** https://linear.app/a8c/project/starter-packs-7bcb9443124c and https://linear.app/a8c/project/starter-packs-abe6585e21f7
**Meetup context:** https://loopp2.wordpress.com/2026/03/19/team-meetup-lisbon-2026-project-idea/

## Current state

### Theme-based packs (7 packs, 34 blogs total)
All blogs scored on a 5-dimension rubric (content quality, reader appeal, brand safety, fediverse fit, visual polish) with 1-5 per dimension, 25 max. Evaluation docs in `evaluations/` folder.

| Pack | Blogs | Score range | Notes |
|------|-------|-------------|-------|
| Food & Drink | 5 | 18-24 | Replaced Graceful Little Honey Bee (ad-choked) with Boston Girl Bakes |
| World Travel | 5 | 17-21 | Replaced Travel with Karla (content drift) with BudgetTraveller. LOTUS EATERS TRAVEL kept despite name similarity to political site. |
| Photography & Visual Arts | 5 | 17-24 | PostSecret kept despite heavy emotional themes (suicide, self-harm in anonymous postcards). Streets of Nuremberg is standout (24). |
| Books & Literary Life | 5 | 18-23 | Strongest pack. Bikozulu (Kenyan writer) is crown jewel. No replacements needed. |
| Economics & Ideas | 4 | 18-24 | Removed Lars P. Syll (crude political language) and Real-World Economics Review (inflammatory reposts). Added Surplus Energy Economics. Conversable Economist is standout (24). |
| Music | 5 | 18-24 | Replaced Kenta (all Japanese) with Brutally Honest Rock Album Reviews. Song of the Day is standout (24). |
| Technology & Science | 5 | 18-23 | Replaced The Technology Geek (inactive, possibly AI-generated) with Schneier on Security. Added Shtetl-Optimized (Scott Aaronson, quantum computing). Removed Promega Connections (corporate blog). |

### Language-based packs (20 packs, ~80 blogs)
Organized in 3 tiers by blog pool size:
- **Tier 1** (100+ active blogs): Japanese, Spanish, French, German, Italian, Portuguese, Dutch, Polish, Chinese Traditional
- **Tier 2** (50-100): Turkish, Russian, Indonesian, Romanian, Swedish
- **Tier 3** (20-50): Greek, Hungarian, Finnish, Korean, Norwegian, Czech

Data from internal analytics DB (blogs.owned_blogs joined with wpcom.blog_properties.lang_id). Blogs ranked by 30-day views, individually verified for language, activity, and content. Arabic pack was removed (no quality blogs available).

### Notable Authors pack (proposed, not yet on page)
Recommended 5 (all confirmed active WordPress+Jetpack):

1. **Seth Godin** (seths.blog) -- 24/25. Marketing icon, daily blogger, 13,886 subs. Minimalist short-form insights.
2. **John Scalzi** (whatever.scalzi.com) -- 22/25. Hugo-winning sci-fi author, daily blogger, 26,689 subs. Personal voice (cats, politics, food, books).
3. **Jenny Lawson / The Bloggess** (thebloggess.com) -- 21/25. NYT bestselling humor/memoir. New book #4 NYT April 2026.
4. **Cory Doctorow** (pluralistic.net) -- 21/25. Author/activist, coined "enshittification." Already has 74K+ Mastodon followers.
5. **Hugh Howey** (hughhowey.com) -- 19/25. Silo/Wool series (Apple TV+ show). Philosophical essays.

**Moonshot:** George R.R. Martin (georgerrmartin.com/notablog/). Self-hosted WordPress but no Jetpack. Would need outreach to install ActivityPub plugin.

## Data sources

- **Subscriber counts:** WordPress.com REST API (`/rest/v1.1/sites/{domain}`)
- **Post counts/dates:** WordPress.com posts API (`/rest/v1.1/sites/{domain}/posts/`)
- **30-day views:** Internal analytics DB (`blogs.owned_blogs.total_30d_views`)
- **Language mapping:** `wpcom.blog_properties.lang_id`
- Jetpack sites return 403 from WP.com API. Subscriber counts are meaningless for Jetpack sites (often show 1).
- All data as of April 12-13, 2026.

## Key design constraints

- All blogs are WordPress.com or Jetpack-connected WordPress (can enable ActivityPub)
- None currently have ActivityPub enabled. Outreach model: "We decided to feature you, let us know if there's any reason we shouldn't."
- Quality criteria: 6-150 posts in 2026, last post at least March 2026, no dead sites, no aggregators, no content farms
- The page is a single index.html deployed via GitHub Pages

## File structure

```
/Users/robpugh/Vibe/starter-packs/
  index.html                          -- main page (GitHub Pages)
  evaluations/
    food-and-drink.md                 -- rubric scores + notes
    world-travel.md
    photography.md
    books.md
    economics.md
    music.md
    technology.md
    prototype-handoff.md              -- this file
```

## Git info

- Repo: gringo-chileno/starter-packs-research
- Use gringo-chileno GitHub account (not robertbpugh)
- Commit with: `-c user.name="gringo-chileno" -c user.email="gringo-chileno@users.noreply.github.com"`
