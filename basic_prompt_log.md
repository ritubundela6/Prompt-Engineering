# Foundational Prompt Log

## Task 1: Text Summarization

### Prompt Input

```text
Summarize the text below in exactly three bullet points. Text: "Remote 
work has rapidly expanded, introducing both opportunities and obstacles for modern businesses..."
```

### ChatGPT Output

```text
- Remote work has expanded rapidly among modern businesses.
- It creates new opportunities for flexibility and organizational growth.
- It also introduces challenges that businesses must address effectively.

You could share the rest of the text for a more complete three-point summary.
```

## Task 2: Information Extraction

### Prompt Input

```text
Extract the customer's name, email address, and order ID from the 
support request below. Support Request: "Hello FlexTime, my name is John Doe (john.doe@email.com). I 
haven't received my shipment updates for order FT-99881. Please check."
```

### ChatGPT Output

```text
- Customer name: John Doe
- Email address: john.doe@email.com
- Order ID: FT-99881
```

## Task 3: Formatting Conversion

### Prompt Input

```text
Convert the list of product prices below into a markdown table with
two columns: "Item" and "Price". List: - Wireless Mouse: $25.00 - Ergonomic Keyboard: $70.00 - Insulated
Water Bottle: $18.00
```

### ChatGPT Output

```text
| Item | Price |
|---|---:|
| Wireless Mouse | $25.00 |
| Ergonomic Keyboard | $70.00 |
| Insulated Water Bottle | $18.00 |
```

## Task 4: Tone Editing

### Prompt Input

```text
Act as an Editor. Rewrite the draft text below to sound like a professional, polite
B2B email sent to a client. Draft: "hey, sorry we are late on the report. it had bugs. we will send it
tomorrow. thanks."
```

### ChatGPT Output

```text
Here’s a polished B2B version:

:::writing{variant="email" id="58321" subject="Report Delivery Update"}
Dear [Client Name],

Please accept our apologies for the delay in delivering the report. We identified and needed to resolve several issues to ensure the report meets our quality standards.

We expect to send the completed report by tomorrow.

Thank you for your patience and understanding.

Best regards,  
[Your Name]
:::

I can also make it more concise, warmer, or more formal if you prefer.
```

## Task 5: Constraint-Driven Output

### Prompt Input

```text
Summarize the sentence below in under 20 words. Do not use the
word "help" or "assist". Sentence: "Our customer success managers are available 24 hours a day to guide
new users and resolve technical account disputes."
```

### ChatGPT Output

```text
Customer success managers provide 24/7 guidance for new users and resolution of technical account disputes.
```
