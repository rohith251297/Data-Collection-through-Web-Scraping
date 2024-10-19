# Data Collection through Web Scraping

## Overview

This project implements a web scraper that fetches and parses HTML content from a specified URL. The scraper extracts the title, headings, and paragraphs from the webpage, filtering the text based on the Tamil, Hindi, and Kannada languages. Additionally, it normalizes the extracted text by removing HTML tags, advertisements, and common stopwords.

## Requirements

Before running the project, ensure you have the following packages installed:

- `requests`
- `beautifulsoup4`
- `langdetect`
- `nltk`
- `indic-nlp-library`

You can install the required libraries using pip:

```bash
pip install requests beautifulsoup4 langdetect nltk indic-nlp-library
```

## Usage

1. Open the Python script containing the web scraper code.
2. Update the `url` variable with the desired URL of a Tamil article.
3. Run the script. The scraper will fetch and print the following:
   - Title of the article
   - All paragraphs from the article
   - Normalized paragraphs in Tamil, free of ads and stopwords.

### Example

```python
url = "https://www.bbc.com/tamil/articles/cdje4levdveo"
scraper = WebScraper(url)
Soup = scraper.scrape()
print(Soup.prettify())
```

## Functions

1. **WebScraper**:
   - Initialization: Accepts a URL and initializes the scraper.
   - `scrape()`: Fetches the HTML content from the URL and returns a BeautifulSoup object.

2. **extract_text_from_page(Soup)**:
   - Extracts the title, headings (h2), and paragraphs (p) from the BeautifulSoup object.

3. **is_target_language(text, target_language='ta')**:
   - Detects if the given text is in the specified language (default is Tamil).
   - Note: Use 'hi' for Hindi, 'ta' for Tamil, and 'kn' for Kannada.

4. **normalize_text(text_list)**:
   - Cleans and normalizes the text by:
     - Removing HTML tags
     - Filtering out advertisements and irrelevant phrases
     - Removing specified punctuation
     - Tokenizing and removing common Tamil stopwords

## Example Output

The output of the script will include the title and paragraphs of the article along with the normalized paragraphs:

```
Title: [Title of the Article]
Paragraph 1: [Normalized Paragraph 1]
Paragraph 2: [Normalized Paragraph 2]
...
```
## Contact
If you have any questions or issues, please feel free to contact Rohith.
