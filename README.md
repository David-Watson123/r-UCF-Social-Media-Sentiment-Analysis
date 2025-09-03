# r/UCF Social Media Sentiment Analysis

**TL;DR:** Collected r/UCF Reddit comments, ran a RoBERTa sentiment model, and visualized topic-level trends. Parking is consistently the most negative topic.

**Headline numbers**

Total comments analyzed: 41,259

Overall sentiment: Negative 38.1% · Neutral 43.9% · Positive 18.0%

Most negative topic: Parking — 51% negative across 893 comments

**Results**

The two provided pngs, depicting both overall sentiment and sentiment by topic

**Skills**

API ingestion with PRAW (Reddit) and comment de-duplication by comment_id

NLP using a transformer (CardiffNLP twitter-roberta-base-sentiment-latest, 3-class)

Topic tagging via concise regex (parking, housing, football, professors, friend(s), party/parties)

Visualization with Matplotlib (publication-ready PNGs)

**How it works**

Collect top posts from all time → pulls all thread comments → skip IDs already seen → append to a master CSV.

Score each comment: negative/neutral/positive with CardiffNLP RoBERTa sentiment model.

Tag topics using regex like:

Parking: \b(?:parking|garage|permit|commute|commuting|commuter)\b

Housing: \b(?:housing|apartment|apartments|lease|rent|rental|roommate|dorms?)\b

Football: (?:\bfootball\b|\bknights\b|\bgame\s+day\b)

Professors: \bprofessors?\b · Friend(s): \bfriends?\b · Party/parties: \bpart(?:y|ies)\b

Visualize overall and by topic using the UCF color scheme.

