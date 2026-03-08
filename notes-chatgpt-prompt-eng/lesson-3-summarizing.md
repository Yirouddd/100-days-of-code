# 📘 Lesson [3]: Summarizing

## 📌 Basic Info
- **Date**: 2026-03-03
- **Status**: ✅ Completed

---

## What is LLM text summarization
Text summarization is the process of using Large Language Models to automatically create a shortened version of a longer text while retaining the most important information and main ideas
  
### Two Main Types:
- **Extractive Summarization**: Pulls key sentences directly from the original text
- **Abstractive（生成式） Summarization**: LLM understands the text and generates new sentences in its own words (more flexible and intelligent)

---

## Summary Techniques
### Summarizing a single text
>  **Length Control**  

```text
prompt = f"""
Summarize the following article below, delimited by triplr backticks, in at most 30 words.

Article content: '''{text}'''
"""

respnse = get_completion(prompt)
print(response)
```

> Target Audience

```text
prompt = f"""Please summarize this text for different audiences:
Generate:
1. For elementary school students (simple language)
2. For professionals (keep technical terms)
3. For executives (highlight key decisions)

Article content: '''{text}'''
"""

respnse = get_completion(prompt)
print(response)
```

> Specific Focus
``` text
prompt = f"""Summarize this article from the following perspectives:
- Main arguments
- Supporting evidence
- Potential issues
- Practical applications
Article content: '''{text}'''
"""

respnse = get_completion(prompt)
print(response)
```
### Summarizing multiple texts simultaneously
> use FOR loop
```python
reviews = reviews[review_1, review_2, review_3]
for i in range((len(reviews)):
  prompt = f"""
  ...
  ...
  Article content: '''{reviews[i]}'''
  """
  respnse = get_completion(prompt)
```

---

## Advanced Summarization Techniques
### Chain Summarization (for very long texts)
```text
Step 1: Split long document into parts, summarize each
Step 2: Combine part summaries, summarize again
Step 3: Get final condensed version
```

work flow example:
```text
Here's Part 1 of my article: [content]
Please create a 100-word summary.

(after completion)
Here's Part 2 of my article: [content]
Please create a 100-word summary.

(after all parts)
Now combine all these part summaries into one 300-word comprehensive summary.
```

### Emphasis-Based Summary
```text
Summarize these meeting notes with special attention to:
- Agreements reached (mark with **)
- Action items (mark with >>)
- Points of disagreement (mark with ??)

Meeting notes:
[paste your text here]
```
