# App Review Analysis Project

Created By: Lalit Agarwal
 
## Dataset Exploration
- It was a app review dataset.
- It was in unstructured format, varying lengths contains emojis.
- Challenges I faced was in Language Variety it contains review in English and hinglish format both
- Presence of typos, misspellings, and grammatical errors
- Many reviews were short and lacks detail
- No header,no line separation (.txt not in csv)

## Preprocessing
Below are the preprocessing steps done on the dataset
- Removed punctuation
- Removed numbers
- Removed whitespace
- Replaced emoji with their text description
- spelling correction(conflicting with hinglish words)
- stop words removal (for sentiment)
- lemmatization( converting it in their base form)
- removed reviews with 2 or less words
- detected hinglish and English reviews as hi and en
- converted hinglish reviews to English using deep translator(google translator)
This resulted in cleaned dataset, language labels, prepared for analysis

## Summarization
- GPT 3.5 free trial was unavailable, so I have used Hugging Face
- I have used BART model from the Hugging Face Transformers library
- Limiting to the summary to 30 words

## Sentiment Analysis
- Here I have created a numerical sentiment score for each review and categorical labels as positive negative
- For Categorical labels I have used Hugging Face Pipeline
- and for numerical sentiment score (-1 to 1) I have used TextBlob
 
## Top Reviews
- Represented top 5 review positive and negative based on their numerical sentiment score

## Limitations
- Spelling Correction: Spell checking was not accurate due to the presence of Hinglish words.
- Language Detection: The heuristic-based method was sometimes affected by typos and misspellings.
- ChatGPT Unavailability: Could not utilize ChatGPT (GPT-3.5) due to resource constraints.

## Potential Model Improvements
- BART model used in this project was pre-trained on general text data.
- Fine-tuning them on a larger dataset of app reviews could significantly improve their performance by tailoring them to the specific language and characteristics of app reviews. (by collecting large corpus of  review from different sources)
- Hinglish Handling: will try advanced models or techniques for Hinglish.
- App based sentiment
- Use ROUGE metric and human evaluation to assess summary quality
- Explore using a different LLM model, such as ChatGPT, for improved language detection, translation, and summarization.
- ChatGPT's strong understanding of language nuances and context could lead to more accurate and readable summaries
- Experiment with using an ensemble of different summarization models or sentiment analysis models.
- Explore building a custom Hinglish-to-English translation model using techniques like sequence-to-sequence learning
