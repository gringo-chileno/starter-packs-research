# Fediverse Starter Packs: Prototype Session Handoff

## What this is

Research page for the ActivityPub WordPress plugin team's Lisbon 2026 meetup project. Curated WordPress blog recommendations organized into starter packs that users can follow on WordPress.com Reader and the fediverse via ActivityPub.

**Live research page:** https://gringo-chileno.github.io/starter-packs-research/
**GitHub repo:** https://github.com/gringo-chileno/starter-packs-research
**Linear projects:** https://linear.app/a8c/project/starter-packs-7bcb9443124c and https://linear.app/a8c/project/starter-packs-abe6585e21f7
**Meetup context:** https://loopp2.wordpress.com/2026/03/19/team-meetup-lisbon-2026-project-idea/

## Current state

### Theme-based packs (8 packs, 39 blogs total)
All blogs scored on a 5-dimension rubric (content quality, reader appeal, brand safety, fediverse fit, visual polish) with 1-5 per dimension, 25 max. Evaluation docs in `evaluations/` folder.

| Pack | Blogs | Score range | Notes |
| --- | --- | --- | --- |
| Food & Drink | 5 | 18-24 | Replaced Graceful Little Honey Bee (ad-choked) with Boston Girl Bakes |
| World Travel | 5 | 17-21 | Replaced Travel with Karla (content drift) with BudgetTraveller. LOTUS EATERS TRAVEL kept despite name similarity to political site. |
| Photography & Visual Arts | 5 | 17-24 | PostSecret kept despite heavy emotional themes (suicide, self-harm in anonymous postcards). Streets of Nuremberg is standout (24). |
| Books & Literary Life | 5 | 18-23 | Strongest pack. Bikozulu (Kenyan writer) is crown jewel. No replacements needed. |
| Economics & Ideas | 4 | 18-24 | Removed Lars P. Syll (crude political language) and Real-World Economics Review (inflammatory reposts). Added Surplus Energy Economics. Conversable Economist is standout (24). |
| Music | 5 | 18-24 | Replaced Kenta (all Japanese) with Brutally Honest Rock Album Reviews. Song of the Day is standout (24). |
| Technology & Science | 5 | 18-23 | Replaced The Technology Geek (inactive, possibly AI-generated) with Schneier on Security. Added Shtetl-Optimized (Scott Aaronson, quantum computing). Removed Promega Connections (corporate blog). |
| Notable Authors | 5 | 19-24 | Seth Godin (24), John Scalzi (22), Jenny Lawson (21), Cory Doctorow (21), Hugh Howey (19). Doctorow already has 74K+ Mastodon followers. |

### Language-based packs (20 packs, ~80 blogs)
Organized in 3 tiers by blog pool size:
- **Tier 1** (100+ active blogs): Japanese, Spanish, French, German, Italian, Portuguese, Dutch, Polish, Chinese Traditional
- **Tier 2** (50-100): Turkish, Russian, Indonesian, Romanian, Swedish
- **Tier 3** (20-50): Greek, Hungarian, Finnish, Korean, Norwegian, Czech

Data from internal analytics DB (blogs.owned_blogs joined with wpcom.blog_properties.lang_id). Blogs ranked by 30-day views, individually verified for language, activity, and content. Arabic pack was removed (no quality blogs available).

### Notable Authors pack (5 blogs, added to page)
All confirmed active WordPress or Jetpack-connected:

1. **Seth Godin** (seths.blog) -- 24/25. Marketing icon, daily blogger, 13,887 subs, 276,820 30d views. Minimalist short-form insights.
2. **John Scalzi** (whatever.scalzi.com) -- 22/25. Hugo-winning sci-fi author, daily blogger, 32,505 subs, 97,536 30d views.
3. **Jenny Lawson / The Bloggess** (thebloggess.com) -- 21/25. NYT bestselling humor/memoir, 16,404 subs, 91,355 30d views. Book #4 hit NYT list April 2026.
4. **Cory Doctorow** (pluralistic.net) -- 21/25. Author/activist, coined "enshittification." Already has 74K+ Mastodon followers. Jetpack site (views not tracked in internal DB).
5. **Hugh Howey** (hughhowey.com) -- 19/25. Silo/Wool series (Apple TV+ show), 2,597 subs, 14,170 30d views. Low posting frequency (5 posts in 2026).

**Moonshot:** George R.R. Martin (georgerrmartin.com/notablog/). Self-hosted WordPress, no Jetpack. Konstantin Obenland suggested outreach on the Strike P2 in Feb 2014 but no follow-through found. Team 51 outreach form at to51outreach.wordpress.com could be used for a new request.

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
/Users/robpugh/work/projects/starter-packs/
  index.html                          -- main page (GitHub Pages)
  evaluations/
    food-and-drink.md                 -- rubric scores + notes
    world-travel.md
    photography.md
    books.md
    economics.md
    music.md
    technology.md
    notable-authors.md               -- rubric scores + notes
    prototype-handoff.md              -- this file
```

## Git info

- Repo: gringo-chileno/starter-packs-research
- Use gringo-chileno GitHub account (not robertbpugh)
- Commit with: `-c user.name="gringo-chileno" -c user.email="gringo-chileno@users.noreply.github.com"`
