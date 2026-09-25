# Prompt Improvement Report

This report compares the six basic-prompt responses (“Before”) with the six responses generated after the structured prompts (“After”). Scores reflect the actual outputs in this conversation, not how well the prompts might perform with all placeholders filled. Each dimension uses a 1–5 scale, where 1 is poor and 5 is excellent. The total is the sum of the four dimension scores, out of 20.

## Comparison table

| Content Task | Prompt Version | Relevance (1-5) | Tone (1-5) | Formatting (1-5) | Length (1-5) | Total Score /20 |
|---|---|---:|---:|---:|---:|---:|
| Blog post: Remote work | Before (Naive) | 4 | 4 | 3 | 4 | 15/20 |
| Blog post: Remote work | After (Optimized) | 5 | 5 | 5 | 4 | 19/20 |
| LinkedIn post: Tech careers | Before (Naive) | 5 | 5 | 4 | 5 | 19/20 |
| LinkedIn post: Tech careers | After (Optimized) | 3 | 5 | 5 | 5 | 18/20 |
| Email campaign: B2B offer | Before (Naive) | 5 | 4 | 5 | 5 | 19/20 |
| Email campaign: B2B offer | After (Optimized) | 4 | 5 | 5 | 5 | 19/20 |
| Instagram caption | Before (Naive) | 5 | 4 | 3 | 5 | 17/20 |
| Instagram caption | After (Optimized) | 2 | 5 | 5 | 5 | 17/20 |
| YouTube video script | Before (Naive) | 5 | 4 | 4 | 4 | 17/20 |
| YouTube video script | After (Optimized) | 4 | 5 | 5 | 3 | 17/20 |
| Product description | Before (Naive) | 5 | 4 | 5 | 4 | 18/20 |
| Product description | After (Optimized) | 2 | 3 | 5 | 5 | 15/20 |

**Scoring note:** Length measures fit for the requested medium and any explicit length requirement, not word count alone. Formatting measures compliance with the requested presentation. The Before and After outputs sometimes use different subjects: for example, the Before email concerns a water bottle, while the After email concerns Bundela company’s B2B digital-transformation offer. Scores therefore assess each response against its own user input rather than pretending the two outputs describe the same product. A tie or lower After score reflects missing input or the actual generated text, not proof that structured prompting is ineffective.

## 1. Blog post: Remote work

### Objective

Write an accessible article about remote work’s benefits; in the optimized version, address B2B managers and provide actionable takeaways.

### The Issue with the Before Prompt

“Write a blog post about why remote work is good” specified the subject but not the reader, decision context, format, or treatment of trade-offs. The resulting article covered common benefits clearly but had no section headings or manager-specific decisions.

### The After Strategy

The RGCCO prompt defined the writer’s role, goal, B2B audience, constraints, and H1/H2/bullet format. A short reference excerpt guided the direct explanatory tone without reusing its wording.

### Quality Comparison Summary

The score rose from **15/20 to 19/20**. The After article addressed hiring, focused work, documentation, and coordination through specific management decisions, and followed the requested heading and takeaway structure. It scored 4/5 on length because it was useful but fairly substantial for a short blog post.

## 2. LinkedIn post: Tech careers

### Objective

Produce a concise LinkedIn post for tech-career readers with a single-sentence hook, a practical insight, a takeaway, and a closing question.

### The Issue with the Before Prompt

The Before request named a concrete topic—learning prompt engineering—but did not set length, hook, emoji, or closing-question rules. Despite this, the response was engaging and well tailored, using an ERP-reporting example.

### The After Strategy

Role prompting set a tech-careers copywriter persona, while zero-shot instructions controlled the hook, structure, tone, maximum length, and emoji count. No example post was provided.

### Quality Comparison Summary

The score moved from **19/20 to 18/20**. The After post met the format and length rules, but `[Insert Topic]` was never replaced. The assistant chose a broad career-development theme rather than the user’s intended, unspecified topic, so relevance dropped to 3/5. The Before post remained more on-target because its topic was explicit.

## 3. Email campaign: B2B offer

### Objective

Write a short sales email with a subject line, preview text, SME-oriented message, and one contact call to action. The Before task instead requested a consumer email about a new water bottle.

### The Issue with the Before Prompt

The water-bottle request omitted product specifications, brand positioning, audience details, and desired action. The response handled that uncertainty with generic copy and placeholders, but could not make a distinctive product claim.

### The After Strategy

A one-shot prompt supplied a model email layout, a B2B copywriter role, Bundela company context, an SME audience, a digital-transformation theme, and a prohibition on invented product claims. It also asked for one clear call to action.

### Quality Comparison Summary

Both versions scored **19/20**. The After response had a more suitable B2B tone and followed the layout, but it still needed a defined `[Insert Product/Offer]` and verified features before it could become a specific sales pitch. The Before email was also coherent and well formatted for its separate, simpler product request. The equal totals do not imply the two offers are interchangeable.

## 4. Instagram caption

### Objective

Create a short, engaging image caption. In the optimized task, reproduce a precise layout: hook with one emoji, a context sentence, and two grouped hashtag lines.

### The Issue with the Before Prompt

The original coffee-cup request did not prescribe structure, number of hashtags, or line spacing. Its response was relevant but minimal: one caption line and a single line of hashtags.

### The After Strategy

Few-shot prompting supplied three captions showing the desired hook, context sentence, blank lines, emoji usage, and hashtag grouping; explicit rules reinforced the pattern.

### Quality Comparison Summary

Both versions scored **17/20**, for different reasons. The After output closely followed the requested spacing and hashtag structure, improving formatting from 3/5 to 5/5. However, `[Insert Image Description]` was never filled in; the assistant assumed a desk photo, lowering relevance from 5/5 to 2/5. The Before caption was unmistakably about the specified coffee cup.

## 5. YouTube video script

### Objective

Write a practical video script. The optimized version aimed to help SME viewers think through digital transformation in the context of Bundela company’s ERP, AI, automation, and workflow offer.

### The Issue with the Before Prompt

“How to start a business” established a topic but not an audience, duration, delivery style, filming cues, or visual layout. The resulting script had helpful stages and some on-camera directions, but it did not use a production-ready split-column format.

### The After Strategy

RGCCO and role prompting specified a professional creator persona, logical sequence, conversational voice, practical example, visual cues, call to action, and a two-column Markdown table. The follow-up instruction supplied Bundela company context from the preceding email.

### Quality Comparison Summary

Both versions scored **17/20**. The After script improved tone and formatting and gave a concrete purchase-request example, but `[Insert Goal]`, `[Insert Topic]`, `[Insert Audience]`, and `[Insert Duration]` were not explicitly filled. It inferred a reasonable SME topic from context, yet its short script could not be checked against a target runtime, lowering its length score to 3/5. The Before script was more directly aligned with its stated topic.

## 6. Product description

### Objective

Turn specifications into a concise, consumer-benefit-led description without inventing features. The Before task concerned a wireless mouse; the After task supplied only “ERP AI digtial product” as the purported specification.

### The Issue with the Before Prompt

“Write a product description for a wireless mouse” gave almost no verified specifications. The response sounded usable, but “comfortable to hold” was not established by the request; the closing note appropriately asked for verified details.

### The After Strategy

Few-shot prompting provided two examples mapping raw specs to benefits, required a 50–80-word paragraph, and prohibited unsupported features or guarantees.

### Quality Comparison Summary

The score fell from **18/20 to 15/20**. The After response satisfied the one-paragraph length and avoided detailed fabricated claims, but the input did not provide actual features or technical specs from which to derive buyer benefits. Its resulting copy was generic, and the final sentence—“Share its specific features to make this description more useful to buyers”—reads like an instruction rather than a finished product description. The remedy is to supply verified ERP/AI product capabilities before rerunning the prompt.
