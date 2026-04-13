# Language Pack Replacement Candidates

## Context

Triage evaluation of all 86 language pack blogs found 6 failures that were removed from index.html. This doc lists replacement candidates from the internal analytics DB for each language. The next session should visit each candidate, verify it is an active blog (not a content farm, e-commerce store, or news portal), and pick the best fit.

## Replacement process

For each candidate:
1. Fetch the homepage and /feed/ via WebFetch
2. Confirm the blog is in the correct language
3. Confirm it is a real blog with editorial voice (not a content farm, aggregator, or pure commercial site)
4. Check brand safety (no hate speech, extremism, adult content, disinformation)
5. Check via WP.com API for subscriber count, post count, and last post date:
   - Subscribers: `https://public-api.wordpress.com/rest/v1.1/sites/{domain}`
   - Posts 2026: `https://public-api.wordpress.com/rest/v1.1/sites/{domain}/posts/?after=2025-12-31T23:59:59Z&number=100&fields=date&status=publish`
   - Jetpack sites return 403 (expected)
6. Score as Pass / Flag / Replace
7. Add the best candidate to index.html

Git commits must use: `-c user.name="gringo-chileno" -c user.email="gringo-chileno@users.noreply.github.com"`

---

## Polish (need 1 replacement)

**Removed:** bacologia.wordpress.com (antisemitic hate speech, conspiracy theories disguised as ecology blog)

**Remaining in pack:** Krwiodawcy (blood donation, 137K views), Niebiescy997 (police news, 125K views), Troche Inna Cukiernia (foraging/baking, 22K views)

**Candidates from DB** (lang_id=58, sorted by 30-day views):

| URL | Name | 30d Views | Notes |
|-----|------|-----------|-------|
| niepodlewam.pl | Niepodlewam.pl | 222,184 | Name means "I don't water." Likely gardening blog. |
| nataliasowierka.pl | Natalia Sowierka | 224,485 | Personal name. Check if blog or portfolio. |
| poliszklarnia.pl | Poliszklarnia | 194,907 | Could be greenhouse/gardening related. |
| kanalwyjazdowy.pl | Kanał Wyjazdowy | 172,775 | "Exit Channel." Possibly travel. |
| kodluch.wordpress.com | KODLUCH | 266,054 | WordPress.com hosted. High views. Check content. |
| wypiekibeaty.com.pl | Wypieki Beaty | 421,013 | "Beata's Baking." Food blog candidate. |
| u-nosek.com | Ula Nosek Fotografia | 600,473 | Photography. High views. |

---

## Norwegian (need 2 replacements)

**Removed:** derimot.no (pro-Russian disinformation), spiselighage.no (e-commerce seed shop, not a blog)

**Remaining in pack:** Det Glade Kjokken (recipes, 1.3M views), Bike (motorcycles, 20K views)

**Candidates from DB** (lang_id=51, sorted by 30-day views):

| URL | Name | 30d Views | Notes |
|-----|------|-----------|-------|
| altasiatisk.no | Alt Asiatisk | 166,593 | "All Asian." Likely Asian food blog. |
| linkaneumann.com | LinkaNeumann.com | 149,391 | Personal name. Check content type. |
| undervisningsmetoder.com | UNDERVISNINGSMETODER | 134,876 | "Teaching Methods." Education resource. |
| lokalen.wordpress.com | NyttiOs.no | 129,985 | WordPress.com hosted. Name suggests health/nutrition. |
| merkbart.no | Merkbart | 90,270 | Unclear. Check content. |
| rundrm.no | RUNDRM | 185,901 | Unclear. Check content. |
| mspa.no | MSPA.no | 150,788 | Unclear. Check content. |

**Excluded:** steigan.no (566K views but documented pro-Russian propaganda, same source as derimot.no), inyheter.no (2.5M, major news portal), ITavisen (1.1M, tech news portal), festutstyr.no (party supplies store), skarpekniver.com (knife e-commerce store)

---

## Romanian (need 2 replacements)

**Removed:** domnuroz.ro (explicit adult erotic fiction), luminaadevarului.com (conspiracy theories, disinformation)

**Remaining in pack:** Carte de Retete (recipes, 174K views), Acoperamantul Maicii Domnului (Orthodox faith, 107K views)

**Candidates from DB** (lang_id=61, sorted by 30-day views):

| URL | Name | 30d Views | Notes |
|-----|------|-----------|-------|
| dulciurifeldefel.ro | Dulciuri fel de fel | 303,431 | "Sweets of all kinds." Baking/desserts blog. |
| nascutpelistaneagra.wordpress.com | Nascut pe lista neagra | 360,565 | "Born on the blacklist." WordPress.com. Check content carefully (high views but name is provocative). |
| gazetar.eu | gazetar.eu | 421,547 | "Journalist." News/opinion. Check editorial quality. |
| learn-online.ro | learn-online.ro | 403,001 | Education platform. Check if blog or just course catalog. |
| artasomnului.ro | Arta Somnului | 427,676 | "The Art of Sleep." Health/wellness. |
| istoriiregasite.wordpress.com | ISTORII REGASITE | 25,158 | "Recovered Histories." WordPress.com. History blog. |
| diacritica.wordpress.com | diacritica | 81,232 | WordPress.com. Name suggests language/writing focus. |
| antoneseiliviu.wordpress.com | @ntonesei's blog | 18,940 | WordPress.com. Personal blog. |

**Excluded:** HotNews.ro, G4Media.ro, B365, Edupedu.ro, StartupCafe (all major news/media portals, not blogs)

---

## Portuguese (need 1 replacement)

**Removed:** meinformei.com.br (content farm with clickbait)

**Remaining in pack:** Portal Zenite (public procurement, 199K views), Tem Alguem Assistindo (TV reviews, 193K views), Ruralea (rural life, 176K views), Oxente Paraiba (regional news, 176K views)

**Candidates from DB** (lang_id=60, sorted by 30-day views):

| URL | Name | 30d Views | Notes |
|-----|------|-----------|-------|
| receitarapido.com | Receita Rapido | 485,588 | "Quick Recipe." Food blog. Check if real blog or content farm. |
| mundodereceitas.com.br | Mundo de Receitas | 457,926 | "World of Recipes." Food blog. Same check needed. |
| onibusetransporte.com | Onibus & Transporte | 484,252 | "Buses & Transport." Niche transport blog. |
| espacoprofessor.com | Espaco do Professor | 433,984 | "Teacher's Space." Education resource. |
| www.arlindovsky.net | Blog DeAr Lindo | 493,813 | Portuguese (PT, not BR). Education/teacher blog. |

**Excluded:** fapello.video (pornography), VEJA/InfoMoney/CNN Brasil (major media), Grupo Mateus (supermarket chain), Simulation World (commercial)

---

## Also flagged (lower priority, user's call)

These were flagged but not removed. The next session can revisit if needed:

| Blog | Language | Issue |
|------|----------|-------|
| airfryertotaal.nl | Dutch | E-commerce site, not really a blog. Legitimate business. |
| yulbin.com | Korean | MapleStory gaming guides, not "personal blog" as labeled. Brand-safe. |
| gaonbit.kr | Korean | Good picture book content but SSL certificate issue. Verify if site loads in browser. |

## Category correction applied

nazarca.com (Turkish) topic changed from "Education" to "Crafts & knitting" in index.html.
