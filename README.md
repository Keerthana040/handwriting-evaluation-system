# Handwritten Text Detection and Answer Evaluation using BERT

# ✍️ Handwriting Detection

A system designed to digitize and analyze handwritten content.  
The primary goal is to **bridge the gap between physical, handwritten documents and their digital, searchable, and editable counterparts**.

## 🚩 Problem Solved

Traditional methods of handling handwritten documents are inefficient and error-prone:

- **Manual Data Entry** → Time-consuming and prone to human error.
- **Lack of Searchability** → Handwritten text is difficult to search across archives.
- **Limited Accessibility** → Physical documents can be lost, damaged, or unavailable remotely.
- **Inefficient Analysis** → Extracting structured data from handwritten content is nearly impossible without digitization.

👉 The **Handwriting Detection system** solves these by leveraging **Optical Character Recognition (OCR)** and **Machine Learning** to convert handwriting into machine-readable data.

## 🏗️ Project Overview

The system is modular and split into distinct components:

- **Frontend** → User interface for uploading documents, initiating detection, and viewing results.
- **Interface** → Manages communication between the frontend and backend via APIs.
- **Recognition** → The OCR engine that extracts handwritten text.
- **Similarity Checker** (optional) → Compares extracted handwriting with known samples or documents to detect patterns.

This modular design ensures independent development, testing, and scaling.

## 🔄 Core Workflow

1. **Document Upload** → User uploads an image or PDF.
2. **Request Initiation** → Frontend sends request to the Interface.
3. **Text Extraction** → Recognition module performs OCR on the document.
4. **Result Processing** → Extracted text returned to frontend for display.
5. **Similarity Analysis (Optional)** → Text checked against samples for patterns.

<img width="1049" height="560" alt="Screenshot 2025-09-22 164446" src="https://github.com/user-attachments/assets/7b5efb1e-e53f-46b1-9afd-13e8a6c738ab" />


## Integration Points

Understanding how these modules interact is crucial for development and debugging:

- **Frontend ↔ Interface**  
  The Frontend communicates with the Interface via defined API endpoints.  
  Any changes to the API contract must be reflected in both components.

- **Interface ↔ Recognition**  
  The Interface acts as a gateway to the Recognition module.  
  It is responsible for passing image data and receiving extracted text.  
  The Recognition module might expose specific functions or endpoints that the Interface calls.

- **Interface ↔ Similarity Checker**  
  Similar to the Recognition module, the Interface orchestrates calls to the Similarity Checker.  
  It passes the extracted text and receives similarity scores or reports.
