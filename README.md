# NLP Word Cloud Generator

This project focuses on performing NLP processing on movie dialogue texts, including tokenization, stopword removal, part-of-speech tagging, named entity recognition, and sentiment analysis, to generate word clouds.

## Prerequisites

- Python 3.7 or higher
- Required Python libraries:
  - `wordcloud`
  - `pillow`
  - `nltk`
  - `matplotlib`
  - `numpy`
  - `re` (standard library)

## Installation

1. Clone this repository or download the script files.

2. Install the required Python libraries:
   ```bash
   pip install wordcloud pillow nltk matplotlib numpy
   ```

3. Download the necessary NLTK data:
   ```python
   import nltk
   nltk.download('stopwords')
   nltk.download('punkt')
   nltk.download('averaged_perceptron_tagger')
   nltk.download('maxent_ne_chunker')
   nltk.download('words')
   nltk.download('vader_lexicon')
   ```

## File Description

- `nlp_wordcloud.py`: The main Python script that performs NLP processing and generates word clouds.
- `assets/`: A directory containing image files used as masks for the word clouds.
  - `butterfly.webp`
  - `car.webp`
  - `dog.webp`
  - `tower.jpg`
  - `tree.jpg`
- `movie_lines.txt`: A text file containing movie dialogue, formatted as follows:
  ```
  L1045 +++$+++ u0 +++$+++ m0 +++$+++ BIANCA +++$+++ They do not!
  L1044 +++$+++ u2 +++$+++ m0 +++$+++ CAMERON +++$+++ They do to!
  L985  +++$+++ u0 +++$+++ m0 +++$+++ BIANCA +++$+++ I hope so.
  L984  +++$+++ u2 +++$+++ m0 +++$+++ CAMERON +++$+++ She okay?
  L925  +++$+++ u0 +++$+++ m0 +++$+++ BIANCA +++$+++ Let's go.
  ```

## Usage

1. Ensure all necessary files (`nlp_wordcloud.py`, `movie_lines.txt`, and the images in the `assets` directory) are in the same directory.

2. Run the script:
   ```bash
   python nlp_wordcloud.py
   ```

3. The script will perform the following steps:
   - **Read and clean the movie dialogue from `movie_lines.txt`**: Extracts the dialogue text and removes special characters and numbers.
   - **Tokenize the cleaned text**: Splits the text into individual words.
   - **Remove stopwords**: Filters out common stopwords (e.g., "the", "is").
   - **Generate word clouds using different image masks**: Creates visual representations of the text data.
   - **Part-of-speech tagging**: Identifies the part of speech for each word (e.g., noun, verb).
   - **Named entity recognition**: Detects and categorizes named entities (e.g., people, organizations, locations).
   - **Sentiment analysis**: Analyzes the overall sentiment of the text (positive, negative, neutral).

4. The word clouds will be displayed, and the NLP analysis results will be printed to the console.

## Detailed NLP Steps

### Text Cleaning
The `clean_text` function removes special characters and numbers from the text to ensure that only meaningful words are processed.

### Tokenization
Uses NLTK's `word_tokenize` to split the text into individual words (tokens).

### Stopword Removal
Uses NLTK's predefined stopword list to remove common stopwords, allowing the focus to remain on more important words.

### Part-of-Speech Tagging
Uses NLTK's `pos_tag` to tag each token with its part of speech (e.g., noun, verb).

### Named Entity Recognition
Uses NLTK's `ne_chunk` to recognize and categorize named entities (e.g., people, organizations).

### Sentiment Analysis
Uses NLTK's VADER (Valence Aware Dictionary and sEntiment Reasoner) to perform sentiment analysis, providing scores for positive, negative, neutral, and overall sentiment.

## Example Output

The script will generate and display the following word clouds:

- A butterfly-shaped word cloud
- A car-shaped word cloud
- A dog-shaped word cloud
- An Eiffel Tower-shaped word cloud
- A tree-shaped word cloud

Additionally, the results of the part-of-speech tagging, named entity recognition, and sentiment analysis will be printed to the console.