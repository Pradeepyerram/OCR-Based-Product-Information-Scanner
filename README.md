OCR-Based Product Information Scanner
====================================

Overview
--------
This project is an OCR-based product information scanner that extracts text from product label images and retrieves matching product details from a MongoDB database.
It is designed to streamline the process of identifying product information directly from images, which can be helpful for inventory management, retail automation, or quick product lookup.

Features
--------
- Extracts text from product images using Tesseract OCR (or EasyOCR, PaddleOCR).
- Cleans and preprocesses extracted text for better accuracy.
- Matches product names, SKUs, or IDs with a MongoDB database.
- Returns full product details including name, price, description, category, stock status, etc.
- Command-line or script-based usage for quick integration into workflows.

Project Structure
-----------------
OCR-Product-Scanner/
│
├── main.py                # Main script to run OCR and fetch product data
├── ocr_module.py          # Handles image reading and OCR extraction
├── db_module.py           # Handles MongoDB connection and product lookup
├── utils.py               # Helper functions (text cleaning, formatting)
│
├── requirements.txt       # Python dependencies
├── config.py              # MongoDB connection config
├── sample_images/         # Folder containing sample product label images
└── README.txt             # Project documentation (this file)

Requirements
------------
- Python 3.8+
- MongoDB (local or remote)
- Install dependencies:
    pip install -r requirements.txt

requirements.txt
----------------
pytesseract
opencv-python
pillow
pymongo
easyocr     # optional (for better OCR accuracy)
numpy

Setup & Installation
--------------------
1. Clone the repository:
    git clone https://github.com/your-username/OCR-Product-Scanner.git
    cd OCR-Product-Scanner

2. Install dependencies:
    pip install -r requirements.txt


3. Add sample data (optional):
    {
      "product_name": "Nutella Hazelnut Spread",
      "sku": "NTL123",
      "price": 350,
      "category": "Food & Beverages",
      "stock": "Available"
    }

Usage
-----
Run the main script with an image path:
    python main.py --image sample_images/nutella.jpg

Example Output:
    Extracted Text: Nutella Hazelnut Spread
    Product Found:
    {
      "product_name": "Nutella Hazelnut Spread",
      "price": 350,
      "category": "Food & Beverages",
      "stock": "Available"
    }

How It Works
------------
1. Input Image → User provides product image path.
2. OCR Processing → Tesseract/EasyOCR extracts text from the image.
3. Text Cleaning → Removes noise, special characters, and formats text.
4. Database Lookup → Searches MongoDB for matching product details.
5. Result Display → Prints or returns structured product information.

Future Improvements
-------------------
- Add GUI/Web Dashboard for easier usage.
- Support barcode/QR code scanning for faster product lookup.
- Improve OCR accuracy using deep learning-based OCR models.
- Deploy as a REST API or Flask/FastAPI service.

Author
------
Developed by yerram pradeep kumar
Email: kpradeep3104@gmail.com
GitHub: https://github.com/Pradeepyerram
