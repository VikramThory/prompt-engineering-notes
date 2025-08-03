# prompt-engineering-notes
A curated collection of notes, examples, and best practices for learning and mastering prompt engineering with large language models (LLMs) like ChatGPT, GPT-4, and others. Covers concepts, patterns, use cases, and techniques for building effective and reliable AI prompts.

# Prompt Engineering with Generative AI: Structured Notes

## Introduction
Prompt Engineering is the art and science of designing effective queries or instructions to get the desired response from a generative AI system. A well-crafted prompt significantly enhances the quality, relevance, and accuracy of AI-generated content.

---

For detailed notes about different aspects of Prompt engineering and how to integrate with different languages and environments, and to find which model is suitable for the specific use cases refer to the official documentation:-
- **ChatGPT** - https://platform.openai.com/docs/overview 

---

## Anatomy of a Prompt
Each prompt can consist of the following components:

### 1. **Persona**
What role should the AI model assume?
- *Example 1:* "As a data analyst preparing a report for executives..."
- *Example 2:* "As a teacher designing a science quiz for 10th-grade students..."
- *Example 3:* "As a customer support agent addressing a technical issue with a product..."

### 2. **Instruction**
What action should the AI take? Typically starts with a verb.
- *Example 1:* "Generate a summary..."
- *Example 2:* "Create a multiple-choice quiz with 5 questions..."
- *Example 3:* "Draft a polite response to a customer complaint about delayed shipping."

### 3. **Input Context**
Relevant text or data to be processed by the model.
- *Example 1:* "...of key findings from the Q2 sales performance dataset."
- *Example 2:* "...from the attached article on climate change."
- *Example 3:* "...based on the transcript of the customer call."

### 4. **Format**
The required format for the output, if any.
- *Example 1:* "Written in natural language with 3-4 insights and one chart recommendation."
- *Example 2:* "Use bullet points and include one real-world example for each point."
- *Example 3:* "Tabular format with columns for Item, Issue, and Resolution."

### 5. **Additional Information**
Helpful context or background to guide the AI.
- *Example 1:* "Avoid technical terms like p-values or regressions; instead, focus on business impact and trends."
- *Example 2:* "Make the tone professional but friendly."
- *Example 3:* "Limit the response to 150 words."

> *Note: Not all prompts will require every component.*

---

## Prompting Strategies

### 1. **Zero-Shot Prompting**
Prompt includes no examples.
- *Best for:* General tasks the model is likely trained on.
- *Example 1:* "Summarize the key features of Amazon S3 for someone new to cloud storage."
- *Example 2:* "Translate this sentence into French."
- *Example 3:* "List three benefits of regular physical exercise."

### 2. **Few-Shot Prompting**
Prompt includes a few examples to guide model behavior.
- *Example 1:* "Suggest five small AI skill projects that a software developer could build in a weekend."
- *Example 2:* "Write a short poem about nature. For example: 'The sun peeks over hills so high / Birds take flight in morning sky.' Now write another."
- *Example 3:* "Reformat these sentences into active voice. Example: 'The ball was thrown by John' -> 'John threw the ball'."

### 3. **Chain-of-Thought Prompting**
Encourages the model to reason step-by-step before giving an answer.
- *Example 1:* "We need to deploy a web app that must scale quickly under variable traffic. Reason step-by-step whether AWS Elastic Beanstalk, Azure App Service, or Kubernetes on GCP would be best."
- *Example 2:* "A train leaves station A at 3:00 PM traveling at 60 km/h. Another train leaves station B at 4:00 PM traveling at 80 km/h. When will they meet? Show your steps."
- *Example 3:* "Evaluate the pros and cons of remote work by considering productivity, communication, and employee satisfaction in sequence."

---

## Evaluation Criteria for AI Responses

### 1. **Accuracy**
- Does the response contain correct and reliable facts?
- *Note:* AI can hallucinate and invent incorrect details.
- *Tips:*
  - Ask AI to cite its sources.
  - Provide key facts up front.
  - Instruct AI to say "I don't know" if unsure.

### 2. **Coherence**
- Does the response follow a logical flow?
- Use chain-of-thought prompting for better structuring.

### 3. **Bias**
- Does the response use inclusive and neutral language?
- Ask the AI to do a self-review for bias.

---

## Evaluation Techniques for AI Responses

### Survey and Interviews
Sample questions for user feedback:
1. Is the information factually correct and relevant?
2. Does the answer stay on topic and flow logically?
3. Is the language clear and easy to understand?
4. Are there signs of bias, stereotypes, or unfair assumptions?
5. Was the response delivered in an appropriate tone?
6. How satisfied are you with the speed of the response?
7. Did the conversation flow naturally?

> *Note: These are example questions to collect feedback from users.*

### A/B Testing
Create two prompts for two user groups and compare feedback.

### Self-Critique Prompting
Ask the AI to evaluate and improve its previous output.
- *Example 1:* "Review your previous response for any inaccuracies, logical gaps, or bias. Then suggest ways to improve it."
- *Example 2:* "Evaluate your last answer for clarity and add missing explanations."
- *Example 3:* "Was your previous response complete and helpful? Revise it if necessary."

---

## How to Reduce Repetition in AI Responses

![How to Reduce Repetition in AI Responses](<img width="1536" height="1024" alt="ChatGPT Image Aug 3, 2025, 11_26_42 PM" src="https://github.com/user-attachments/assets/ca892769-6ba0-4a0a-a78e-57584af331b9" />
)

- **Vary the Prompt Design:** Add examples or change the structure of instruction.
- **Use Parameters Smartly:** Adjust temperature and top_p to increase response diversity.
- **Inject Contextual Anchors:** Refer to prior conversation or domain-specific keywords.
- **Control Format Explicitly:** Ask for varied phrasing, tone, or perspective.

---

## Common Model Parameters

1. **Max Tokens**
   - Controls output length (and cost).
   - 1 token ≈ 1 word or punctuation.

2. **Temperature**
   - Controls creativity.
   - Higher = more creative, Lower = more deterministic.

3. **Top P (Nucleus Sampling)**
   - Controls randomness by narrowing output to top X% most likely options.

4. **Stop Sequence**
   - Defines where the model should stop generating output.

---

## Advanced Evaluation Metrics

1. **BLEU (Bilingual Evaluation Understudy)**
2. **ROUGE (Recall-Oriented Understudy for Gisting Evaluation)**
3. **Perplexity**
4. **BERTScore**
5. **SummC**

> *These metrics evaluate semantic similarity and summarization accuracy.*

> *Note: Tune your model settings (e.g., Max Tokens, Temperature, Top P, Top K, Stop Sequence) for better performance.*

---

## General Strategies for Better Prompting

1. **Be Clear on the Objective**
   - Use action verbs, specify output format.

2. **Offer Background and Context**
   - Provide facts, data, documents.

3. **Be Specific**
   - Use precise language, break down tasks.

4. **Iterate and Refine**
   - Try different prompt lengths, phrasing, and detail levels.

5. **Ask for Self-Reflection**
   - Request the AI to check for assumptions or reasoning errors.

---

## Categorizing Feedback: Examples

- **Feedback:** "It's hard to find the settings menu."
  - *Category:* Usability Issue

- **Feedback:** "The app crashed twice today when uploading files."
  - *Category:* Bug Report

- **Feedback:** "I wish there was a dark mode option."
  - *Category:* Feature Request

---

## Summary
Prompt engineering is a vital skill in leveraging the power of generative AI. By understanding prompt structure, evaluation metrics, and feedback techniques, you can greatly enhance the quality and reliability of AI responses. Always strive for clarity, inclusivity, and precision in both your prompts and evaluation strategies.

