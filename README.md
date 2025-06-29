# 🛍 Product Image to Shopping Assistant

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![OpenCV](https://img.shields.io/badge/OCR-EasyOCR-orange)
![LLM](https://img.shields.io/badge/LLM-Ollama%20%7C%20LLaMA3.2-brightgreen)

> This project transforms product images into intelligent shopping insights using OCR, generative AI, and real-time search summarization. It helps users find similar or better alternatives across major e-commerce platforms.

---

##  Features

-  **Image-based Product Detection**  
  Extracts text from any image (e.g. a product label or screenshot) using `EasyOCR`.

-  **AI-Generated Search Queries**  
  Uses `Ollama` + `LLaMA3.2` to convert noisy extracted text into clean, user-friendly search queries.

-  **E-Commerce Aggregation**  
  Redirects users to relevant product listings from **Amazon**, **Flipkart**, and **eBay**.

-  **Smart Summarization of Listings**  
  Scrapes search result pages and summarizes listing trends, prices, offers, and brand mentions using LLM-based summarization.

-  **Modular Design**  
  All functionalities are split into self-contained components: `OCR`, `Search Generator`, `Web Scraper`, `Summarizer`.

---

##  Project Structure

```bash
.
├── assets/                 # Folder containing product image(s)
├── main.py                # Main application pipeline
├── old_main.py            # Legacy version (no summarization)
├── image_utils.py         # OCR extraction using EasyOCR
├── search_utils.py        # Search query generation using LLaMA3.2
├── web_scraper.py         # Builds product search links
├── summarizer.py          # Summarizes listing content from search pages
├── requirements.txt       # Python dependencies
