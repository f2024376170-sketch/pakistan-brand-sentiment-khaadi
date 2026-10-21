# 🇵🇰 Pakistani Social Media Content Detective: Khaadi

## 1. Business Question
**"What type of social-media content gets Pakistani audiences to engage, and what should a Pakistani brand do next?"**

We acted as junior digital-marketing data scientists for the brand **Khaadi** (a leading Pakistani fashion brand). We collected audience comments from Pakistan-region YouTube videos, measured sentiment and engagement, found patterns, and generated a data-driven marketing recommendation.

## 2. Data
- **Source:** YouTube Data API v3 (region: Pakistan)
- **Brand:** Khaadi
- **Videos searched:** 439, of which the 60 most-commented Khaadi-related videos were kept (6 from the official Khaadi channel, the rest from creators and vloggers)
- **Comments collected:** 2,022 (2,005 after cleaning)
- **Languages:** English 1,338 | Roman Urdu 597 | Urdu 70
- **Engagement metric:** comment likes + replies

## 3. Methodology
1. **Collection:** YouTube API (videos, statistics, comments, timestamps)
2. **Cleaning:** lowercase, URL removal, emoji-to-text, Roman Urdu spelling normalization, language detection (Urdu / Roman Urdu / English), timestamps converted to Pakistan time (PKT)
3. **Sentiment model:** multilingual transformer `cardiffnlp/twitter-xlm-roberta-base-sentiment` (positive / neutral / negative)
4. **Analysis:** engagement by content type, sentiment, hour, day, language, hashtags
5. **Complaint mining:** keyword-theme analysis on negative comments (fashion-specific themes)
6. **Big data processing:** PySpark used for aggregations (sentiment, language, hour, day)
7. **Recommendation:** rule-based, data-driven marketing recommendation

## 4. Results

### Sentiment distribution
| Sentiment | Comments | Share |
|---|---|---|
| Positive | 839 | 42% |
| Neutral | 717 | 36% |
| Negative | 449 | 22% |

### The 7 project questions
| # | Question | Finding |
|---|---|---|
| 1 | Which platform performs better? | Only YouTube was analysed (see limitations), so no cross-platform comparison was made. |
| 2 | Which content type gets more engagement? | **Medium-length videos (1-5 min)** |
| 3 | Popular topics / hashtags | #khaadi, #khaadisale, #khaadinewcollection, #khaadipret, #shopping |
| 4 | What sentiment generates engagement? | **Positive** comments received the highest average engagement |
| 5 | Best time / day | **Friday, around 11:00 AM PKT** |
| 6 | Which audience segment is more responsive? | **Roman Urdu** commenters had the highest average engagement, although English is the largest segment (1,338 comments) |
| 7 | What should the brand post next? | See recommendation below |

### What needs improvement? (complaint themes in negative comments)
| Theme | Negative comments |
|---|---|
| Price / Expensive | 32 |
| Sale / Discount | 31 |
| Delivery / Online | 19 |
| Fabric / Quality | 8 |
| Customer Service | 8 |
| Stock / Availability | 8 |
| Size / Fit | 4 |
| Return / Refund | 1 |

## 5. Marketing Recommendation for Khaadi
1. **Content:** Publish medium-length (1-5 min) videos, which earned the most engagement.
2. **Timing:** Post on Friday around 11:00 AM PKT.
3. **Language:** Write captions and replies in Roman Urdu (with English for wider reach), since Roman Urdu commenters were the most engaged.
4. **Hashtags:** #khaadi, #khaadisale, #khaadinewcollection, #khaadipret, #shopping.
5. **Fix first:** pricing perception, sale and discount communication, and delivery/online experience. These are the top complaint themes.
6. **Community management:** Positive comments earn the most engagement, so reply quickly to fans and feature happy customers to build on that momentum.

## 6. Limitations
- **Only YouTube** was used. Free APIs for Facebook, Instagram and TikTok are not available, so platform comparison was not possible.
- Only **6 of 60 videos** are from the official Khaadi channel. The rest are creator, vlogger and haul videos, so the comments reflect broader public opinion about the brand rather than only official content.
- Only **449 comments are negative**, so complaint theme counts are small and should be read as indicative, not conclusive.
- The multilingual sentiment model is **less accurate on Roman Urdu** (code-mixing, spelling variation, sarcasm). Some comments may be mislabeled.
- Engagement is based on **comment likes + replies**, not post-level likes, shares or views.
- Complaint themes use **keyword matching**, which can miss context.
- Best hour/day reflects *when comments were posted*, not necessarily when videos were published.

## 7. Tech Stack
Python, Google Colab, YouTube Data API v3, pandas, Hugging Face Transformers (XLM-RoBERTa), matplotlib, PySpark

## 8. Files
- `khaadi_sentiment_project.ipynb`: full notebook (code and outputs, including all charts)
- `final_data (1).csv`: cleaned dataset with sentiment labels

## 9.
Arooj Fatima Malik
f2024376170
Course: Big Data Analytics
