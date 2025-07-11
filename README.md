Questions to ask vendor

1. What's the architecture
2. How much noise can the model tolerate without significant drop in performance
3. Average noise in test set
4. Speed distribution of speakers in training set
5. Open source/built from scratch
6. How are punctuations handled
7. What datasets are used for training
8. How was data cleaning and pre processing done
9. Any data augmentations done? 
10. Any domain specific fine tuning done?
11. Metric the model was trained on
12. Speaker demography 
13. What's the latency
14. What's the RTF
15. Confidence scores


Evaluating STT models

Metrics: 
1. Sentence error rate (SER): how many sentences have at least one error
2. Real time factor (RTF): time taken to transcribe /audio length
3. Latency: Time delay between transcription and audio
4. Confidence scores: confidence percentage for transcription
5. Out of vocabulary (OOV) accuracy: how frequently OOV words are correctly transcribed
6. Rhyming words error rate: how often model mistakenly transcribes a word to its rhyming word (struggles to differentiate between rhyming words)
7. Homophone accuracy: how often model confuses between homophones (to and two, their and there)

Tests: 
1. Age: Children vs adult vs elderly
2. Multiple speakers
3. Variable volume
4. Audio source: laptop/phone/headphone mic, indoor vs outdoor
5. Domain specific vocabulary recall
6. Sentence boundary detection
7. Punctuation detection
8. Capitalisation of proper nouns


Quant Cafe email

Subject: LLMs are now taking notes! 📋

Hi everyone,

LLMs have now learnt that outsourcing specialized tasks and organizing information in a structured format helps them reason better than several cutting edge reasoning models.

In this discussion on “Agentic Reasoning: Reasoning LLMs with Tools for the Deep Research” we will dive into a cutting-edge framework that enables language models to use tools like web search, code execution, and structured memory to solve complex, multi-step problems.

We’ll explore how this approach:
1. Enhances reasoning using external agents
2. Uses a Mind Map to build knowledge graphs from reasoning
3. Outperforms GPT-4 and others on PhD-level question answers and deep research tasks

It's a great chance to discuss the future of tool-augmented LLMs and discover how similar smart AI agents are to us.

