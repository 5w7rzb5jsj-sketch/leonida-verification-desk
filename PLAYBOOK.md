# Verified Feed — Operating Playbook

The verified discovery desk for GTA 6. We don't compete on speed, because every large account is fast. We compete on being **visibly right**: every claim labelled, every discoverer credited, every viral fake called out.

## 1. Rules (non-negotiable)

1. **No leaks, no datamines, no pre-release material.** Rockstar's video policy lists these as takedown content, and Take-Two enforces it (it sent a cease-and-desist over a fan RDR2 mod in November 2026). One leak post can cost the whole account.
2. **No story spoilers in the first 72 hours**, and none in titles or thumbnails ever.
3. **Credit every discoverer by handle.** That's the moat: discoverers tag you, and you never get accused of lifting work.
4. **No Rockstar logos or official art in the brand.** "GTA6" goes in plain text only. Name the account something like `LeonidaVerified`, not `GTA6_Official`.
5. **Console only.** There is no PC version at launch, so never post PC hardware advice.
6. **Corrections are public.** A correction post builds more trust than it costs.

## 2. The loop (per claim)

| Step | Action | Sheet column |
|---|---|---|
| Spot | Claim appears on r/GTA6, X, Discord or TikTok | `found_utc`, `discoverer`, `source_url`, `claim` |
| Label | Post **UNVERIFIED** immediately if it's spreading | `status` = Unverified |
| Check | Go there in-game. Screenshot/clip from **your own** save | `verified_by` |
| Resolve | Re-post as **VERIFIED** or **FALSE**, quoting the original | `status`, `posted_utc` |
| Log | Link the post; map claims to `marker_id` where relevant | `post_url`, `marker_id` |

`post_text` builds itself from the row, so copy and post. `lag_min` calculates itself.

## 3. Platforms

- **X**: primary. Breaking verified and false posts. Quote-repost the discoverer.
- **TikTok / Shorts**: 15–30 s clip of *your own* gameplay at the spot. Caption = post_text.
- **Discord**: free server = the feed plus a `#report-a-find` channel (your sourcing pipeline).
- **Reddit**: comment the verification under the original thread with credit. Don't spam links.

## 4. Revenue, in order of reliability

1. **Sponsorships** (weeks 2–6). Pitch with the Feed stats sheet: claims checked, debunk rate, median minutes to post. Accessory and peripheral brands are the targets. Newsletter benchmarks: about **$150–300 per sponsored slot** under 20k subscribers.
2. **Relevant affiliates.** The install is about 212 GB. Console storage expansion is a real, timely purchase. Always label posts "(affiliate)" (FTC rules).
3. **Paid Discord tier (optional, after 2k+ engaged members).** Sell *organized* value, not a head start: completion routes, per-region collectible checklists, and a weekly verified digest. Expect 12–18% monthly churn; price for retention.
4. **Licensing the record.** Debunks and corrections flow into `corrections.json`. Map sites (mapheist invites corrections) are the buyers.

## 5. Metrics that matter

- Median time to post (sponsor headline)
- Debunk share (proof you filter, not just repeat)
- Discoverers credited (community goodwill)
- Corrections issued (trust signal; zero corrections means you're not checking hard enough)

## 6. Launch calendar

| When | Do |
|---|---|
| Now–18 Nov | Claim handles on X, TikTok, Discord. Pin the rules post. Build the `#report-a-find` channel. |
| 19 Nov, unlock | Live. Unverified → verify → resolve. Debunk early fakes hard; they spread fastest. |
| Days 2–7 | Daily "verified this week" thread. First sponsor outreach with real numbers. |
| Weeks 2–6 | Collectible routes per region; paid tier if engagement supports it. |
| Q1 2027 | PC launch = second discovery wave. Same playbook. |
