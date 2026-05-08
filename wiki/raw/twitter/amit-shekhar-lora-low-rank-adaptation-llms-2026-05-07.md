---
source_url: https://x.com/i/status/2052344905004171507
ingested: 2026-05-07
---

# LoRA - Low-Rank Adaptation of LLMs

**Author:** Amit Shekhar (@amitiitbhu), Verified account  
**Engagement:** 22 reposts, 121 likes, 123 bookmarks, 5636 views  
**Post ID:** 2052344905004171507  

In this blog, we will learn about LoRA - Low-Rank Adaptation of Large Language Models.

Today, we will cover the following topics:  
- The Big Picture  
- Why Full Fine-Tuning Is Expensive  
- The Core Idea Behind LoRA  
- How LoRA Works Step by Step  
- A Small Numeric Example  
- Where LoRA Is Applied in a Transformer  
- Merging LoRA Back Into the Model  
- Real-World Use Cases  
- Quick Summary  

I am Amit Shekhar, Founder @ [[Outcome School]], I have taught and mentored many developers... passionate about sharing knowledge through open-source, blogs, and videos. I teach [[AI and Machine Learning]] at Outcome School.  

## The Big Picture  
Before we go into the details, let's understand the big picture.  

LoRA is a way to fine-tune a large model without updating all of its weights. Instead of changing the original weight matrix, we keep it frozen and learn a tiny pair of extra matrices on the side. These tiny matrices capture the \"adjustment\" we want.  

**In simple words:** LoRA = Frozen original weights + A small low-rank update learned on the side.  

This makes fine-tuning much cheaper, faster, and lighter on storage. And, we still get strong task-specific performance.  

## Why Full Fine-Tuning Is Expensive  
... (content truncated in scrape; full article likely at linked blog. Extracted via browser snapshot on 2026-05-07)