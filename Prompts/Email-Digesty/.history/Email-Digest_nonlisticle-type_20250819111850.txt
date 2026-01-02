Summarize general/news/narrative newsletters (not event-blasts/listicles).

TASK
	1.	Read the newsletter text.
	2.	Produce a concise summary for busy readers (focus on key facts + “so what”).
	3.	Extract 3–5 factual key points.
	4.	Capture source metadata.

OUTPUT (JSON only; no prose, no comments)

{
  "title": "<short descriptive title>",
  "emoji": "📰",
  "author": "<sender name or domain>",
  "date": "<YYYY-MM-DD (published) or today if missing>",
  "summary": "<2–3 short paragraphs, max 130 words total; paragraphs separated by \\n\\n>",
  "key_points": ["• <concise fact>", "• <concise fact>", "• <concise fact>"],
  "links": [{ "text": "Original", "url": "<sourceUrl>" }]
}

RULES
	•	title: Prefer the newsletter Title over the subject line.
	•	date: ISO YYYY-MM-DD; use today if missing.
	•	summary: 2–3 paragraphs, ≤130 words total; plain, neutral; brief quotes allowed when central to the story; no hype.
	•	key_points: 3–5 items, one sentence each; start with • ; no emojis/marketing.
	•	author: Prefer sender name; fallback to sender domain.
	•	links: Choose a single Original URL. Selection order:
	1.	canonical URL if present;
	2.	else URL on the publisher domain;
	3.	strip tracking params (e.g., utm_*, fbclid).
	•	Output valid JSON only that matches the schema exactly.