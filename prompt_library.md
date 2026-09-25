# Prompt Library

The following prompt-engineering requests and assistant outputs are arranged in the order they appeared in the conversation. The assistant outputs are reusable prompts, not completed posts or campaigns.

## 1. Blog post: RGCCO framework and style transfer

### User request

> Blog Post (RGCCO Framework + Style Transfer): Find a short reference text from a popular blog post whose style you admire. Construct a prompt defining the Role (expert blog writer), Goal (write a blog post), Context (benefits of remote work for B2B managers), Constraints (no corporate fluff, active voice, short paragraphs), and Output Format (H1 title, H2 sections, bulleted takeaways). Inject the Style Transfer instruction: "Write in the style of the following text: [Insert Reference Text]".

### Assistant output

Here’s a ready-to-use RGCCO prompt. I chose a short excerpt from Paul Graham’s blog post “Maker’s Schedule, Manager’s Schedule” because it opens with a concrete workplace problem and explains it in plain language. [web:18]

> **Role:** You are an expert blog writer who writes practical articles for B2B leaders.
>
> **Goal:** Write a blog post explaining why remote work can benefit B2B managers and their teams.
>
> **Context:** Your readers manage client-facing and cross-functional teams. Address benefits such as access to talent, time for focused work, and clearer documentation. Acknowledge that remote work needs deliberate communication and coordination; do not present it as a solution to every workplace problem.
>
> **Constraints:** Avoid corporate fluff, clichés, and unsupported statistics. Use active voice, short paragraphs, and concrete examples. Make each benefit relevant to a manager’s decisions.
>
> **Output format:** Begin with an H1 title. Use H2 headings for the main sections. End with a short bulleted list of actionable takeaways.
>
> **Style transfer:** Write in the style of the following text: “One reason programmers dislike meetings so much is that they're on a different type of schedule from other people. Meetings cost them more.” [web:18]
>
> Use the excerpt as a guide to its clear, direct explanation of a familiar problem. Write an original post; do not reuse its wording or examples.

## 2. LinkedIn post: Role prompting and zero-shot

### User request

> LinkedIn Post (Role Prompting + Zero-Shot): Instruct ChatGPT: "Act as an expert Social Media Copywriter specializing in tech careers. Write a LinkedIn post about [Insert Topic]..." Include strict constraints: under 150 words, no more than 2 emojis, and a single sentence hook.

### Assistant output

Use this zero-shot prompt and replace **[Insert Topic]** with your chosen subject:

> Act as an expert Social Media Copywriter specializing in tech careers. Write a LinkedIn post about [Insert Topic] for professionals exploring or advancing their careers in tech.
>
> Start with a hook that is exactly one sentence. Follow it with a practical insight and one specific takeaway. End with a question that invites discussion.
>
> Keep the entire post under 150 words. Use no more than 2 emojis. Write in a clear, human-sounding voice and avoid clichés, exaggerated claims, and generic motivational language.
>
> Output only the finished LinkedIn post.

## 3. Email campaign: One-shot prompting

### User request

> Email Campaign (One-Shot Prompting): Provide ChatGPT with one high-performing email layout example using role and context instructions. Structure the prompt around the example email template and then request: "Now, write a B2B sales email promoting our new [Insert Product/Offer]."

### Assistant output

Copy and paste this one-shot prompt into ChatGPT. Replace the bracketed fields before using it.

> **Role:** Act as a B2B email copywriter who writes concise, persuasive sales emails.
>
> **Context:** We are [Company Name]. Our audience is [Target Buyer and Industry]. We want to introduce [Insert Product/Offer] and encourage recipients to [Desired Action]. Use only the product details I provide; do not invent features, results, customer quotes, or discounts.
>
> **Example email layout to follow:**
>
> **Subject:** A simpler way to handle [specific task]  
> **Preview text:** See how [product category] could help your team with [specific goal].
>
> Hi [First Name],
>
> Managing [specific task] can take time away from [important priority].
>
> [Product Name] helps [target audience] [specific, verified benefit] by [brief explanation of how it works].
>
> If improving [relevant outcome] is a priority, I’d be happy to show you how it works.
>
> **[Book a Demo]**
>
> Best,  
> [Sender Name]  
> [Company Name]
>
> **Instructions:** Follow the example’s structure and concise tone, but write original copy tailored to the product and buyer. Keep paragraphs short, use one clear call to action, and avoid hype. If essential product information is missing, use a clearly labeled placeholder rather than guessing.
>
> **Now, write a B2B sales email promoting our new [Insert Product/Offer].**

## 4. Instagram caption: Few-shot prompting

### User request

> Instagram Caption (Few-Shot Prompting): Draft 3 different examples of engaging Instagram captions incorporating hooks, emojis, and grouped hashtags. Input these examples into your prompt so ChatGPT learns the exact structure and spacing required for [Insert Image Description].

### Assistant output

Copy this few-shot prompt into ChatGPT and replace **[Insert Image Description]** with your photo’s details:

> Act as an Instagram copywriter. Write one caption for **[Insert Image Description]** using the exact structure and spacing shown in these examples.
>
> **Example 1 — Coffee cup**
>
> A little pause looks good from here. ☕
>
> Taking a moment to slow down and enjoy the first sip.
>
> #CoffeeMoment #CoffeeBreak #SlowMornings  
> #EverydayJoy #MorningRitual
>
> **Example 2 — Desk setup**
>
> New day, fresh page. ✨
>
> A tidy desk and one clear priority—that’s enough to get started.
>
> #DeskSetup #WorkdayRoutine #FreshStart  
> #FocusTime #SimpleHabits
>
> **Example 3 — Sunset walk**
>
> Sometimes the best plan is to step outside. 🌅
>
> Ending the day with fresh air and a view worth stopping for.
>
> #SunsetWalk #EveningLight #OutsideTime  
> #LittleMoments #TakeABreath
>
> **Now write the caption for [Insert Image Description].** Start with a one-sentence hook containing one relevant emoji. Leave one blank line, then write one short sentence that adds context. Leave another blank line, then add exactly two lines of relevant hashtags, with three hashtags on the first line and two on the second. Output only the caption.

## 5. YouTube video script: Role prompting and RGCCO

### User request

> YouTube Video Script (Role Prompting + RGCCO): Construct a detailed RGCCO prompt setting the Role to "Professional YouTube Video Creator". Under Output Format, specify a split-column markdown layout with Left Column: [Visual/Camera Cue] and Right Column: [Spoken Voiceover Script] for the topic [Insert Goal] about [Insert Topic].

### Assistant output

Copy this RGCCO prompt into ChatGPT and replace the bracketed fields:

> **Role:** Act as a Professional YouTube Video Creator skilled at writing clear, engaging scripts.
>
> **Goal:** Create a YouTube video script that helps viewers [Insert Goal] about [Insert Topic].
>
> **Context:** The target audience is [Insert Audience]. They currently know [Insert Knowledge Level] about the topic. The video should run for approximately [Insert Duration] minutes and leave viewers able to [Insert Desired Outcome].
>
> **Constraints:**
> - Open with a one-sentence hook that gives viewers a reason to keep watching.
> - Explain the topic in a logical sequence using plain language and one practical example.
> - Keep the spoken script conversational and suitable for reading aloud.
> - Avoid filler, exaggerated claims, and unsupported facts.
> - Include visual cues that a creator can realistically film or edit.
> - End with a brief recap and one relevant call to action.
>
> **Output Format:** Write the script as a split-column Markdown table. Label the left column **[Visual/Camera Cue]** and the right column **[Spoken Voiceover Script]**. Use one row per scene or segment, in viewing order. Put only filming, on-screen text, or editing directions in the left column; put only words to be spoken in the right column. Do not add text outside the table.

## 6. Product description: Few-shot prompting

### User request

> Product Description (Few-Shot Prompting): Create 2 examples showing a raw list of technical specifications transformed into an emotionally compelling product description highlighting consumer benefits. Then request the same for [Insert Specs].

### Assistant output

Copy this few-shot prompt into ChatGPT, then replace **[Insert Specs]** with your product’s specifications:

> Act as an e-commerce copywriter. Turn technical specifications into a concise product description that helps shoppers picture how the product fits into their day. Lead with a practical benefit, connect features to real-life use, and keep the tone warm and credible. Use only the supplied specifications; do not invent performance claims.
>
> **Example 1**
>
> **Raw specs:** Wireless mouse; Bluetooth connection; rechargeable battery; USB-C charging; adjustable cursor sensitivity; left- and right-handed design.
>
> **Product description:** Make room to work your way. This wireless mouse connects over Bluetooth, so you can move without a cable across your desk. Adjust the cursor sensitivity to suit the task, then recharge with USB-C when needed. Its left- and right-handed design makes it a flexible choice for your everyday setup.
>
> **Example 2**
>
> **Raw specs:** Water bottle; 750 ml capacity; stainless steel body; leak-resistant lid; carry handle; dishwasher-safe lid.
>
> **Product description:** Keep water close as your day moves along. The 750 ml capacity gives you plenty to carry between refills, while the handle makes the bottle easy to grab on your way out. A leak-resistant lid helps when it’s packed in your bag, and the dishwasher-safe lid makes cleanup simpler.
>
> **Now transform these raw specs into a product description:** [Insert Specs]
>
> Write one paragraph of 50–80 words. Highlight consumer benefits without adding features or guarantees that the specs do not support. Output only the finished description.
