#  Student RAG Assistant

An Arabic-friendly student assistant chatbot that uses **RAG (Retrieval-Augmented Generation)** powered by **Google Gemini** and built on **[n8n](https://n8n.io)**.

This system automatically retrieves relevant PDF files from **Google Drive**, extracts the content, and feeds it along with the student’s question into a powerful AI model to generate accurate educational answers.

---

## Project Overview

This project enables students to ask questions through a simple chatbot interface. The backend workflow will:

1. Search for educational PDFs in Google Drive
2. Download the matched file
3. Extract text from the PDF
4. Pass the question + extracted text to Gemini
5. Generate a smart answer
6. Send the response back to the frontend

All steps are automated using a visual workflow in n8n.

---

##  What is RAG?

**RAG (Retrieval-Augmented Generation)** combines:

- **Retrieval** of knowledge from trusted sources (PDFs, documents, etc.)
- **Generation** using an AI model like Gemini to create a relevant response

This method boosts accuracy and reduces hallucination compared to pure generative models.

---

##  Workflow Breakdown

| Step | Node |
|------|------|
| `Webhook` | Receives the question from the chatbot (POST) |
| `Search Files and Folders` | Searches Google Drive for a relevant PDF |
| `Download File` | Downloads the selected file |
| `Extract from File` | Extracts readable text from the PDF |
| `AI Agent + Gemini Model` | Uses Google Gemini to generate a contextual response |
| `Respond to Webhook` | Sends the final reply back to the user |

---

##  Workflow Diagram

<img width="2048" height="604" alt="image" src="https://github.com/user-attachments/assets/45552175-0dab-40be-a73b-558f29b7d891" />


---

##  Requirements

-  Google Drive account with educational PDFs
-  Google Gemini API credentials
-  n8n account (self-hosted or cloud)
-  Proper authentication setup in n8n:
  - Google Drive OAuth2
  - Gemini (via AI Agent node)

---

##  Project Structure

