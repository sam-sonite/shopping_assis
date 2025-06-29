# Product Image to Shopping Assistant

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Platform](https://img.shields.io/badge/Platform-Desktop%20%7C%20CLI-orange)

> This project transforms product images into intelligent shopping insights using OCR, generative AI, and real-time search summarization. It helps users find similar or better alternatives across major e-commerce platforms.

---

## Tech Stack & Dependencies

| Dependency | Badge |
|------------|-------|
|  **LLM Backend** | [![Ollama](https://img.shields.io/badge/Ollama-0.1.6-ff69b4)](https://ollama.com) |
|  **OCR Engine** | [![EasyOCR](https://img.shields.io/badge/EasyOCR-1.7.1-orange)](https://github.com/JaidedAI/EasyOCR) |
|  **Image Processing** | [![Pillow](https://img.shields.io/badge/Pillow-10.2.0-yellow)](https://python-pillow.org) |
|  **Web Scraping** | [![BeautifulSoup4](https://img.shields.io/badge/bs4-4.12.3-purple)](https://www.crummy.com/software/BeautifulSoup/) [![Requests](https://img.shields.io/badge/requests-2.31.0-blue)](https://requests.readthedocs.io) |
|  **Browser Automation** | [![Selenium](https://img.shields.io/badge/Selenium-4.18.1-green)](https://selenium.dev) |
|  **Torch Runtime** | [![Torch](https://img.shields.io/badge/Torch-2.2.1-red)](https://pytorch.org) [![Torchvision](https://img.shields.io/badge/Torchvision-0.17.1-lightgrey)](https://pytorch.org/vision/stable/index.html) |
|  **Search API** | [![SerpAPI](https://img.shields.io/badge/SerpAPI-2.4.2-blueviolet)](https://serpapi.com/) |

---

##  Features

-  **Image-based Product Detection**
-  **LLM-Generated Search Queries**
-  **Cross-Platform Search (Amazon, Flipkart, eBay)**
-  **Smart Summarization of Listings**
-  **Modular & Extensible Codebase**

---

##  Project Structure

```
.
├── assets/                 # Folder containing product image(s)
├── main.py                # Main application pipeline
├── old_main.py            # Legacy version (no summarization)
├── image_utils.py         # OCR extraction using EasyOCR
├── search_utils.py        # Search query generation using LLaMA3.2
├── web_scraper.py         # Builds product search links
├── summarizer.py          # Summarizes listing content from search pages
├── requirements.txt       # Python dependencies
```

---

##  Setup

```bash
# 1. Clone the repository
git clone https://github.com/your-username/product-image-to-shopping-assistant.git
cd product-image-to-shopping-assistant

# 2. Create and activate your Python environment (optional)
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Place a product image inside the 'assets/' folder

# 5. Run the pipeline
python main.py
```

>  Ensure [Ollama](https://ollama.com) is installed and the `llama3.2:3b-instruct-fp16` model is pulled using `ollama run llama3.2`.

---

##  Behind the Scenes

1. **OCR Engine** (`EasyOCR`) detects product text from an image.
2. **Query Generator** uses LLM (`Ollama + LLaMA3.2`) to create a Flipkart-style search.
3. **Web Search Redirects** return links for Amazon, Flipkart, and eBay.
4. **HTML Scraper** collects product snippets using `requests + bs4`.
5. **Summary Engine** processes snippets into short brand/price/offer summaries using LLM.

---

##  Sample Flow

> Given image of a product package like:

`assets/noisebuds.png`

You’ll get:
```
Extracted Text:
"Noise Buds VS104 Max | 45H Playtime | ENC | ₹1299"

Search Query:
noise buds max with enc under 1500

Results:
✔ Amazon
✔ Flipkart
✔ eBay

Summaries:
Flipkart: Offers from Noise, boAt, Realme. Prices ~₹999–₹1499. Several under ₹1300 with 13mm drivers.
```

---

