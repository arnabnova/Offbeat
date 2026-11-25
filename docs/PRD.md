PRD: Authentic Travel Assistant
Nov 24, 2026 · @Arnab
1. Overview
OffBeat (working name) is a travel assistant that turns a destination plus a traveler's hobbies into a personalized list of places beyond the guidebook, each with its speciality, how to reach it, where to stay, where to eat and six practical tips. Everything is fetched live for the destination; no place or suggestion is hardcoded.
Problem. Tourists tired of the same overcrowded landmarks want authentic local experiences, hidden neighborhood spots and cultural activities, but cannot easily reach local insiders who can curate off-the-beaten-path plans matched to their interests. Validation scores for this problem: severity 7, whitespace 8, frequency 8, TAM 70, overall itch score 63.5.
Vision. For every supported city, a traveler should get a plan that feels like it was written by a local friend who knows their taste, not by a popularity ranking.
What the user does.
1.  Enters a destination and where they are starting from.
2.  Picks one or more traveler modes (Classic, Explorer, Photographer, Foodie, History buff, Budget) and their hobbies.
3.  Gets ranked places with description, area type, scenery type, travel, stay, food and tips, on a map.
2. Goals, non-goals and success metrics
The MVP succeeds if a traveler can get a trustworthy, personalized plan for any of the 30 launch cities, built from live data, in under two minutes.
Goals
• Recommend places that match the traveler's mode and hobbies, not just the most popular ones.
• Explain each place: what makes it special, what kind of area it is, and why it suits this user.
• Give everything needed to act on it: how to reach it, where to stay, where to eat, and six tips.
• Never invent places, prices or timings.
Non-goals (for now)
• Booking flights, trains or hotels inside the app.
• Hand-curated or stored place lists. All place data comes from live sources.
• A full social network or live chat between travelers and locals.
Success metrics
Metric
Target for MVP
Why it matters
Time to first plan
Under 2 minutes
Proves the flow is light
Plans saved or exported
30% of sessions
Shows the plan is useful enough to keep
Tip helpfulness votes
70% positive
Checks the tips are worth reading
Share of non-landmark places opened
40% or more
Checks the app really takes users off the beaten path
Factual error reports
Under 2% of places
Guards trust in the data
Launch scope. The app launches with 30 cities and grows in batches. The supported city list is a setting in the database (name, country, coordinates, status), not place data: places, stays, food and tips for each city are still fetched live. A city joins the list only after it passes the readiness check in section 9.
3. Target users and traveler modes
Primary users are leisure travelers, mostly 18 to 40, who have already seen the standard list and want something that fits how they like to travel. Students, solo travelers and small friend groups are the first audience.
Each mode is a preset that changes how places are ranked and which extra details are shown. Users can combine two modes, which blends their weights.
Mode
Who it is for
Boosted
Extra shown on the card
Classic
First-timers who want the essentials
Popular landmarks
Ticket and timing tips
Explorer
People who want to leave the tourist trail
High rating, few reviews
Why locals love it
Photographer
Anyone shooting photos or video
Viewpoints, architecture, markets
Best light, crowd level, permit notes
Foodie
Travelers who plan around meals
Street food, local eateries
Dishes to try, best time
History buff
Heritage and culture seekers
Monuments, museums, old quarters
Short historical context
Budget
Students and backpackers
Free and cheap places
Estimated daily cost
4. Core user flow
The flow has five steps and should take under two minutes to reach a first result.
1.  Destination. The user types a place. Autocomplete confirms it is a supported destination.
2.  Preferences. The user picks one or two modes, selects hobbies (trekking, street photography, cafes, temples, birdwatching, shopping), sets the scenery preference (natural, man-made or both), and answers four quick questions: days, budget level, group type, and pace (relaxed or packed).
3.  Results. The app shows ranked place cards and a map. Each card carries the place name, description, speciality, area type, scenery type, a match reason, travel info, stay and food nearby, and six tips.
4.  Refine. The user adjusts with chips or chat: "less crowded", "more food", "swap this stop", "only villages".
5.  Save and share. The user saves the plan, downloads it as a PDF, or shares a link.
5. Place intelligence: area type, scenery and speciality
Every place is labelled on three independent axes, so users can filter by what they actually want: a lively city lane, a quiet village, or an undeveloped natural stretch. The labels are worked out live from map tags (such as the settlement type in OpenStreetMap), distance to the nearest town and services, and Wikipedia text; none are entered by hand.
Axis 1: Area type
Area type
Meaning
Traveler expectation set by the app
Metro city
Large urban core
Dense, well connected, crowded at peak hours
Town
Mid-size settlement
Local markets, easier pace
Village
Small rural settlement
Limited facilities, authentic daily life
Underdeveloped / remote
Few facilities or roads
Carry cash and supplies, plan transport ahead
Protected nature area
Park, reserve, forest, coast
Permits, seasonal access, strict rules
Axis 2: Scenery type
Scenery type
Examples
Natural beauty
Hills, rivers, lakes, forests, beaches, sunrise points
Man-made beauty
Monuments, temples, bridges, old quarters, street art, markets
Mixed
Heritage sites inside gardens, fort on a hill, riverside ghats
Axis 3: Speciality tag
A short label for what the place is known for, which also drives the one-line description. The LLM summarises it from live Wikipedia, Wikivoyage and review text, and the card shows the source. Examples: sunrise viewpoint, century-old sweet shop, colonial architecture, street-food lane, pottery village, birdwatching wetland, local craft market, hidden courtyard, quiet riverside walk.
Supporting labels on each place
• Crowd level: quiet, moderate, busy, with a best-time window.
• Authenticity score: how locally rooted the place is, based on local-language reviews and low tourist-tag density.
• Effort level: easy, moderate or demanding to reach and explore.
• Season fit: best months and months to avoid.
• Accessibility note: step-free, rough terrain, or not suitable for limited mobility.
The app should always show the area type up front, so a user never arrives at a remote spot expecting city facilities.
6. Feature list
Priority key: P0 = needed for MVP, P1 = next release, P2 = later delighter. Features marked "yours" came from your requirements; the rest are my additions.
A. Core features
#
Feature
What it does
Priority
Origin
1
Destination search
Enter a place with autocomplete over the supported city list, resolved live to coordinates
P0
Yours
2
Traveler modes
Six modes, combinable, each with its own weights
P0
Yours
3
Hobby and interest picker
Tags like trekking, street photography, cafes, temples, birdwatching
P0
Yours
4
Scenery preference
Natural, man-made or both
P0
Yours
5
Place name and description
Short description rewritten to mention the user's hobbies
P0
Yours
6
Area type label
Metro city, town, village, remote, protected nature area
P0
Yours
7
Speciality tag
One line on what the place is known for
P0
Yours
8
How to travel
Distance, suggested mode and rough time, locally and from the user's origin
P0
Yours
9
Where to stay
Hotels and hostels near the place, filtered by budget
P0
Yours
10
Nearest restaurants
Eateries within about 1 km, ranked for the user's taste
P0
Yours
11
Six helpful tips
One tip each from a fixed set of slots, chosen by mode
P0
Yours
12
Map view
All places, stays and food on a map with route order
P0
Added
B. Differentiators that make it feel like a local friend
#
Feature
What it does
Priority
13
Hidden-gem score
Ranks high-rated, low-review places higher in Explorer mode
P0
14
"Why this suits you" line
Names the hobby and mode that matched
P0
15
Authenticity and crowd badges
Shows quiet, moderate or busy and a best-time window
P1
16
Swap this stop
Replaces one place with a similar but quieter or different one
P1
17
Chat refinement
"Less crowded", "more food", "only villages" re-ranks the plan
P1
18
Day-by-day itinerary
Groups stops by distance and opening hours into a day plan
P1
19
Base-area stay suggestion
Recommends one area to stay in, near the average of the top picks
P1
20
Local contributions
Locals add a spot or tip with a reason, reviewed before it goes live
P1
21
Local phrases and etiquette
A few words, dress code, bargaining and photo rules
P1
C. Trust, safety and practicality
#
Feature
What it does
Priority
22
Source and freshness stamp
Shows where a fact came from and when it was checked
P1
23
Report a problem
One tap to flag a closed or wrong place
P1
24
Safety and scam notes
Common overcharging and crowd risks for that area
P1
25
Remote-area readiness
For villages and remote spots: cash, network, water, last transport
P1
26
Accessibility filter
Step-free and low-effort options
P2
27
Weather-aware suggestions
Moves outdoor stops away from rainy days
P2
D. Delighters
#
Feature
What it does
Priority
28
Offline plan
Saved plan and map tiles usable without network
P2
29
PDF and share link
Export or send the plan to friends
P1
30
Group planning
Friends vote on stops and the plan merges their interests
P2
31
Trip scrapbook
Photos and notes tied to each stop after the trip
P2
32
Multilingual interface
Hindi, Bengali and English first
P2
33
Eco and responsible-travel flag
Marks places that benefit local communities and warns about fragile sites
P2
34
Hidden-gem of the day
Daily surprise suggestion for browsing users
P2
E. Accounts and user data
#
Feature
What it does
Priority
35
Accounts and sign-in
Email or Google sign-in; guests can plan and sign in when saving
P0
36
Saved trips and history
Stores plans so they can be reopened and edited from any device
P0
37
Saved preferences
Remembers modes, hobbies, budget and pace so the next plan starts prefilled
P1
38
Wishlist
Save single places for later without building a full plan
P1
39
Feedback loop
Tip votes and problem reports are stored and used to re-rank results
P1
40
Export and delete my data
Users download or erase everything stored about them
P1
41
Private share links
Share a trip by link, with an expiry date
P1
F. Live data (no stored place content)
#
Feature
What it does
Priority
42
Live place discovery
Fetches places for any destination from map and places APIs at request time, never from a stored list
P0
43
Live stays and restaurants
Searches for nearby hotels and eateries on request, with current ratings and price levels
P0
44
Open now and hours
Shows whether a place is open now and its hours, fetched live
P0
45
Live weather
Shows current weather and forecast on each card; feeds best time and what to carry
P1
46
Live travel times
Distance and time by walking, transit or driving from a routing API
P1
47
Short-lived cache
Keeps recent API responses briefly to cut cost and delay, within each provider's terms
P0
48
Hide empty slots
Any detail with no live source is left out instead of guessed
P0
G. City coverage (launch with 30, grow in batches)
#
Feature
What it does
Priority
49
Supported city list
The 30 launch cities held as a setting in the database (name, country, coordinates, status); search matches against it
P0
50
City readiness check
A test run before a city goes live: do the live sources return enough places, Wikipedia or Wikivoyage text and routes?
P0
51
Coverage level badge
Each city shows rich, ok or limited coverage so users know what to expect
P1
52
Request a city
Users ask for a city that is not listed; requests help choose the next batch
P1
53
Add cities without code
Adding a city means adding a row, then running the readiness check
P1
7. Place card specification
Each recommended place is shown as one card with the fields below, in this order.
Section
Content
Source (all live)
Header
Name, speciality tag, area type, scenery type
Places API and OpenStreetMap, with labels derived at request time
Description
2 to 3 sentences, mentioning the user's hobbies
Wikipedia and Wikivoyage text, rewritten by the LLM
Why it suits you
One line naming the matched mode and hobby
Scoring engine
Badges
Open now, crowd estimate, effort level, best season
Places API hours, review counts and weather; the crowd level is an estimate
How to reach
Distance and time from the user's stay or origin, suggested transport
Routing API
Where to stay
Up to 3 options within 2 km, filtered by budget
Places API, searched on request
Nearest restaurants
Up to 3 within 1 km, with rating and price level
Places API, searched on request
Six tips
One short tip per slot (below)
Live data and Wikivoyage, phrased by the LLM
Feedback
Helpful or not helpful on each tip, report a problem
Users
Sources
Where each fact came from and when it was fetched
Added to every field
The six tips
Tips are drawn from fixed slots so each card is balanced. The mode decides which six are chosen and in what order. Every tip is built from live data fetched for that place (opening hours, weather, price level, Wikivoyage and review text) and shows its source. A slot with no sourced fact is skipped, never filled with a guess.
Slot
What it covers
Best time
Time of day and season, crowd level
Getting around
Easiest way in, last transport
Money
Entry fee, cash vs UPI, typical meal cost
Etiquette and dress
Dress code, footwear, photography rules
Safety and scams
Crowded-area risks, overpriced rides, unofficial guides
What to carry
Water, cash, umbrella, camera gear
Pair it with
A nearby spot or restaurant that fits well
Seven slots exist so there is always a spare when one has no data; the card shows six.
8. Recommendation engine
Code chooses the places and the LLM only explains them. This keeps results predictable and stops the model from inventing or misplacing spots.
Step 1: score each place on seven features (0 to 1), computed at request time from live API data.
Feature
How it is computed
popularity
Review count, log-scaled and normalized
hidden_gem
High rating combined with low review count
photo
Viewpoint, architecture, market and street-art tags, plus phrases like "sunrise" in reviews
food
Street food, local eatery and food-market tags, minus chains
heritage
Monument, museum, old quarter and temple tags, plus Wikipedia presence
affordability
Entry fee and price level, inverted
hobby_match
Overlap between the user's hobbies and the place's tags
Step 2: each mode is a weight vector (starting values, to be tuned on the demo city).
Mode
popularity
hidden_gem
photo
food
heritage
affordability
Classic
0.60
0.00
0.10
0.10
0.15
0.05
Explorer
0.00
0.60
0.10
0.10
0.10
0.10
Photographer
0.10
0.20
0.60
0.00
0.10
0.00
Foodie
0.10
0.20
0.00
0.60
0.00
0.10
History buff
0.10
0.10
0.00
0.00
0.70
0.10
Budget
0.10
0.20
0.05
0.10
0.05
0.50
Step 3: final score. Hobby match is added on top, and the user's scenery and area-type choices act as filters or boosts.
score(p) = \sum_{f} w_{mode,f} \cdot x_{p,f} + \lambda \cdot hobby\_match(p) + \mu \cdot scenery\_fit(p)
When two modes are chosen, their weight vectors are averaged. Starting values for the hobby and scenery terms are 0.25 each, to be tuned.
Step 4: assemble the plan. Take the top places, group them by distance, pick a base area to stay, then attach stays, restaurants and tips by live nearby searches around each place's coordinates.
Configuration, not data. The mode weights and the map from hobbies to place categories are settings kept in the user database and editable without redeploying. They contain no places or suggestions.
Where the LLM is used
• Rewrite place descriptions to mention the user's hobbies.
• Phrase the six tips from verified facts only ("using only the facts below, do not add new facts").
• Handle chat refinement by translating requests like "less crowded" into changed weights or filters.
• It never picks places, fees, opening hours or distances.
9. Data sources and schema
No place, hotel, restaurant or suggestion is stored or hardcoded in the app. Everything is fetched live for the destination when the user asks, and kept in a short-lived cache only to save time and cost. The only data stored permanently is user-created: accounts, plans and feedback (see "User data and accounts" below).
Live sources
Data
Live source options
Used for
Destination and area type
Nominatim or Photon geocoding on OpenStreetMap; Google Places autocomplete
Coordinates, settlement type, distance to nearest town
Places and categories
Overpass API (OpenStreetMap); Google Places or Foursquare Places API
Finding candidate places around the destination
Ratings, review counts, price level, hours
Google Places or Foursquare
Popularity, hidden-gem and affordability scores; open now
Description, history, etiquette and safety notes
Wikipedia and Wikivoyage APIs
Description, speciality, tips
Weather
Open-Meteo or a similar weather API
Best time, what to carry, outdoor ranking
Travel time and routes
OSRM, OpenRouteService or Google Directions
How to reach, day order
Stays and restaurants
The same places APIs, with category filters
Nearby stay and food lookups
Photos
Wikimedia Commons or the places API
Place cards, with licence and credit shown
Read each provider's terms and free limits before building. Some forbid long-term storage of their data, which is why caching is short-lived and only provider ids are kept.
How one request works
1.  Resolve the destination to coordinates and an area type.
2.  Fetch candidate places around it from the places APIs, in parallel.
3.  Enrich the best candidates with Wikipedia and Wikivoyage text, opening hours and weather.
4.  Turn each result into the place shape below, score it, and rank it for the user's modes and hobbies.
5.  For the final picks, fetch nearby stays, restaurants and travel times.
6.  Ask the LLM to write descriptions and tips from the retrieved text only.
7.  Stream the results to the page and cache the responses briefly.
Place shape (built for each request, not stored)
Field
Source
Example
provider_id, name, lat, lon
Places API or OpenStreetMap

categories, tags
Places API or OpenStreetMap
viewpoint, market, temple
area_type
Derived live from map tags and distance to services
village
scenery_type
Derived from categories
natural, man_made, mixed
rating, review_count, price_level
Places API
4.6, 312, 1
open_now, hours
Places API
open until 6 pm
extract, source_url
Wikipedia or Wikivoyage
short text with link
weather_at_visit
Weather API
dry, 26 C
feature scores (0 to 1)
Computed from the fields above
hidden_gem 0.82
sources and fetched_at
Added to every field
shown on the card
User data and accounts
User data lives in its own database, separate from the place data. That lets it have its own access rules and be deleted on request without touching place content. A relational database such as PostgreSQL fits, because plans, places and feedback are linked records.
Table
Stores
Key fields
users
Account and sign-in
id, email or sign-in provider id, display name, language, created_at
preferences
Default modes and hobbies
user_id, modes, hobbies, scenery_pref, budget_level, group_type, pace
trips
One planning session
id, user_id, destination, origin, days, status (draft or saved), created_at
trip_stops
Places in a plan, in order
trip_id, place_id, day, position, note, swapped_from
saved_places
Wishlist of places
user_id, place_id, saved_at
tip_feedback
Helpful or not helpful votes
user_id, place_id, tip_slot, vote, created_at
reports
Wrong or closed place reports
user_id, place_id, reason, status
contributions
Local places and tips awaiting review
user_id, place_id (optional), body, status (pending, approved, rejected)
trip_shares
Private share links
trip_id, token, expires_at
Rules for user data
• Places are referenced by the provider's place id plus a minimal snapshot (name and coordinates); everything else is fetched live when a saved plan is opened.
• Guests can plan without an account and are asked to sign in only when they save.
• Users can read and write only their own rows; reviewers alone can see pending contributions.
• Store only what the features need. Ask before using device location, and do not keep a location history.
• Users can export and delete all their data from their profile.
• Check the data protection rules that apply to your users (for India, the DPDP Act) before launch.
• Feedback votes and reports are the main input for re-ranking tips and hidden-gem scores later.
Supported cities
The launch list and every later batch live in the database as settings. They contain no place data.
Table
Stores
Key fields
cities
Supported destinations
id, name, country, lat, lon, status (testing, live, paused), coverage_level (rich, ok, limited), added_at
city_requests
Cities users ask for
user_id, city_name, created_at
Readiness check for a new city
• The places source returns enough places in at least three categories around the city centre.
• Wikipedia or Wikivoyage has text for the city and for several of its top places.
• The routing source returns travel times between the city's main areas.
• Hotels and restaurants are found within the stay and food search radii.
• The city gets a coverage level (rich, ok or limited); a city with too little data stays in testing and is not shown to users.
Expansion. Add cities in batches (for example ten at a time), check usage and data quality after each batch, and use the city requests to choose the next batch.
10. Technical architecture and suggested stack
The whole product is one Next.js project: the browser app and the server route handlers live together, with no separate backend service. For each request the server fetches live data, ranks it, and asks the LLM to explain only what was retrieved; the user database holds accounts, saved plans and feedback.
Layer
Choice
Notes
Frontend
Next.js (App Router) with React and TypeScript
Server components for fast first load; client components for the map and filters
Backend
Next.js route handlers and server actions
No separate backend service
Live data
Server-side fetches to places, Wikipedia, weather and routing APIs, run in parallel
API keys stay on the server; results streamed to the page
Cache
Short-lived cache (Next.js data cache or a database table with expiry)
Lifetime set by each provider's terms
User database
PostgreSQL, for example Supabase
Accounts, trips, feedback; row-level security
Auth
Supabase Auth or Auth.js
Email and Google sign-in
Maps
MapLibre GL or Leaflet with OpenStreetMap tiles
Check the tile usage policy
Ranking
TypeScript scoring module using the weights from section 8
Weights kept in the database as settings
Hobby matching
Category mapping, plus an LLM or embeddings API for free-text hobbies
No Python or separate ML service
LLM
A hosted LLM API called from route handlers and streamed to the UI
Prompt contains only retrieved text
Hosting
Vercel or similar
API keys as environment variables
11. Roadmap and MVP scope
Phases are equal bands, not to scale; no dates are set yet. The MVP stays small on purpose: all six modes and the P0 features from section 6, launching in 30 cities, all fed by live data.
Suggested build order for the MVP
1.  Set up the Next.js project, the user database and sign-in.
2.  Build destination search over the supported city list, with live geocoding and the area-type lookup.
3.  Add live place discovery from a places API and OpenStreetMap, and turn results into one place shape.
4.  Implement scoring with the mode weights, and check each mode's top 10 on a sample from each of the 30 cities, and record a coverage level (rich, ok or limited) for each.
5.  Build the results page: map, place cards, and filters for mode, hobbies and scenery.
6.  Add live stays, restaurants, opening hours, weather and travel times for each pick.
7.  Add the six tip slots built from retrieved text with their sources, then the LLM phrasing step.
8.  Add caching, rate-limit handling and hidden empty slots, then test with real travelers in the launch cities. After launch, add new cities in batches once each passes the readiness check.
12. Risks, mitigations and open questions
The biggest risks are wrong facts and the cost and speed of fetching everything live, because one bad tip breaks trust and a slow page loses the user.
Risk
Impact
Mitigation
LLM invents places, fees or timings
High
Places come only from API results; the LLM sees retrieved text only; a slot with no source is hidden
API cost and rate limits, since every request is live
High
Short-lived cache, parallel fetches, per-user request limits, fall back to free sources (OpenStreetMap, Wikipedia)
Slow pages from several live calls
High
Fetch in parallel, stream results as they arrive, show the map first
API keys exposed
High
Keep every key on the server in route handlers
Data quality differs across the 30 cities
Medium
Run the readiness check, record a coverage level per city and show it on the card
Usage grows with each added city
Medium
Cache per city, add cities in batches, watch usage after each batch
Provider terms restrict storing or reusing data
Medium
Read terms early; cache only as allowed; keep provider ids, not copies
Tips on etiquette, safety and scams have no clean live source
Medium
Use Wikivoyage sections and review text, show the source, and hide the slot when nothing is found
Thin or uneven data for villages and remote areas
Medium
Label low-confidence results; lean on OpenStreetMap and Wikivoyage
Crowd level and hidden-gem score are estimates
Medium
Label them as estimates; refine with user feedback votes
Promoting fragile sites to more visitors
Medium
Responsible-travel flag; show visitor rules for protected areas
Scope creep
Medium
Hold the MVP to the P0 list
Open questions
• Which 30 cities launch first, and in what order should later batches follow? A mix of big cities, mid-size towns, heritage towns and a few village-rich or remote regions will show where live data is thin.
• Which places API will you use: Google Places (best coverage, paid beyond a free allowance), Foursquare, or OpenStreetMap only (free, but thinner ratings and hours; see section 13)?
• Is this for a hackathon, a portfolio piece or a startup? That decides the budget for API calls.
• English only for the MVP, or Hindi and Bengali too?
13. Free build (zero-cost alternative)
The free build keeps all six modes and every P0 feature except the ones that depend on ratings, prices or reviews, which are replaced by open-data proxies or hidden. It uses only free tiers and open data, so it suits a hackathon, a portfolio piece or an early pilot. Free-tier limits and terms change, so check each provider's current page before you rely on it.
Free stack
Layer
Free choice
Limit to watch
App and server
Next.js on Vercel Hobby plan
Hobby is meant for non-commercial use; function time limits are short, so fetch in parallel and stream
User database and auth
Supabase free tier
Small storage; inactive projects can pause
Destination search
Photon or Nominatim (OpenStreetMap)
Nominatim bans search-as-you-type, so search on submit or use Photon
Places and categories
OpenStreetMap through the Overpass API
Public servers have fair-use limits; keep search radius small and cache results
Descriptions and tips
Wikipedia and Wikivoyage APIs
Thin coverage for small villages
Popularity signals
Wikipedia pageviews API and Wikidata
Only places with an article have a signal
Photos
Wikimedia Commons
Show licence and credit
Weather, sunrise and sunset
Open-Meteo
Free for non-commercial use
Travel time
OSRM or OpenRouteService (free key)
Public servers are rate-limited; no public transit
Map
MapLibre with a free tile provider
The default OpenStreetMap tile server is not meant for app traffic
LLM
A free tier such as Gemini or Groq
Rate limits; check data-use terms and send no personal user data
Replacing the paid signals
Feature score
Paid build
Free build proxy
popularity
Review count
Wikipedia pageviews and the number of language editions on Wikidata
hidden_gem
High rating, few reviews
The place has a quality signal (a Wikipedia article or rich heritage and tourism tags) but low pageviews and few language editions
photo
Tags plus review phrases
Viewpoint, historic, artwork and market tags, plus how many Wikimedia Commons photos are tagged nearby
food
Tags minus chains
Amenity and cuisine tags, with places that carry a brand tag treated as chains
heritage
Tags plus Wikipedia
Historic and heritage tags plus Wikipedia and Wikidata presence
affordability
Entry fee and price level
Fee and charge tags; parks, temples and viewpoints count as low cost; unknown stays neutral and is shown as "price not available"
What is cut or reduced
Feature
In the free build
Ratings and review counts
Cut; replaced by the proxies above
Hotel and restaurant ratings and prices
Cut; cards show name, type, cuisine and distance, with a link to the map
Opening hours and open now
Reduced; shown only where OpenStreetMap has hours
Crowd level badge (feature 15)
Cut; "best time" uses sunrise, sunset and weather instead
Review-based safety and scam tips
Cut; those slots come from Wikivoyage only, or are hidden
Authenticity score from local-language reviews
Cut; replaced by an "under the radar" label from the hidden-gem proxy
Public transit directions
Cut; walking, cycling and driving estimates only
Place photos
Reduced; Wikimedia Commons only
Everything else stays: the six modes, hobbies, scenery choice, area type, speciality, stays and food by distance, tips from Wikivoyage and weather, the map, accounts, saved trips, export and share links.
Design rule: keep the data source swappable
Put all place lookups behind one provider interface in the code. The free build implements it with OpenStreetMap and Wikimedia data. If you later add budget, a Google Places or Foursquare implementation can replace it without changing the interface, the scoring or the pages.
Free-tier cautions
• Call every external API from the server, never the browser, and cache responses so public servers are not hit twice for the same query.
• Several free tiers forbid commercial use. If the app gains real traffic or revenue, plan to move to paid plans or self-host.
• Results will be thinner in places with sparse map data, so label low-confidence results and hide empty slots.
14. Visual design
The app should feel like a photo-led travel app at dusk: misty landscapes, soft glass cards, large light headlines and warm glowing accents. It is designed for phones first. The design canvas "OffBeat: look and feel" shows three phone screens (home, your plan, place detail); use it as the reference when building the UI. The canvas uses drawn scenes as stand-ins for photographs.
Look
Element
Direction
Mood
Dark, calm and atmospheric: deep teal-slate backgrounds, mist, a warm amber glow
Colours
Slate #0E2A33 (background), near-white #F2F7F7 (text), amber #F4A259 (buttons and highlights), glass panels of dark teal at about 60% opacity with a thin white border
Type
Outfit, a clean geometric sans (free on Google Fonts), in a light weight for large headlines and regular weights for text
Cards
Rounded, translucent "glass" panels with a background blur, sitting over a full-bleed photograph
Buttons
Large rounded buttons, amber with dark text for the main action; chips for modes and hobbies that scroll sideways on a phone
Icons
One line-icon set (for example Lucide, free); no emoji
Photography
• The home screen and every place card are led by a real photograph with a dark overlay so white text stays readable.
• Place photos come from Wikimedia Commons, with the credit and licence shown on the card.
• Home and header photos come from a free-licence source such as Unsplash or Pexels; check each photo's licence and keep a credit in the app's about page.
• A place with no photo gets a dark, misty illustrated scene matched to its scenery type, so a card never shows an empty box.
• Do not use photos copied from other websites.
Screens
• Home: full-screen photo, the headline "Beyond the beaten path", and a glass search card with destination, days, mode chips, hobby chips, scenery choice and the "Plan my trip" button.
• Your plan: a photo header with the city and the chosen modes, then a scrolling list of glass place cards, each with photo, area type, scenery, crowd estimate, speciality, reach, stay, eat and a link to details.
• Place detail: a large photo with the place name over it, the description, why it suits the traveler, how to reach it, stay and eat cards, the six tips with their sources, and add-to-trip and report buttons.
• Wide screens: the same screens widen into a two-column layout, with the place list on one side and a map on the other.
Behaviour and quality
• Loading shows skeleton cards, and places appear as they arrive.
• Text on photos always sits on a dark overlay or glass panel and meets contrast guidelines.
• Touch targets are at least 44 px and icon-only buttons have labels.
• Crowd level and similar guesses are always marked as estimates.