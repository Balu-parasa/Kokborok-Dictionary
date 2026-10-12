# Kokborok Dictionary & Translator Project

This project is a comprehensive Kokborok-English dictionary application that combines static dataset lookups with AI-powered analysis.

## 🔄 Project Workflow (End-to-End)

This section describes the complete flow of data from user input to the final response.

### 1. User Input
The user interacts with the application in two ways:
*   **Text Input:** Typing a word or phrase into the search bar.
*   **Voice Input:** Using the microphone button (Web Speech API) to speak Kokborok words.

### 2. Processing & Lookup
Once input is received, the application performs two parallel operations:

#### A. Dictionary Lookup (Static Data)
*   **Technique:** The app searches through specific JSON datasets located in `src/data/`.
*   **Files Used:**
    *   `dictionary.json`: Main glossary extracted from the PDF dictionary.
    *   `numbers.json`: Specialized dataset for Kokborok numerals.
*   **Logic:** The system cleans the input (removes punctuation, lowercases) and searches for matches in the `kokborok` or `english` fields of the JSON data.
*   **Result:** Exact matches or phrase matches are returned immediately.

#### B. AI Analysis (Generative AI)
*   **Technique:** If the user requests "Analyze", the input is sent to the **Google Gemini API**.
*   **Model:** Uses `gemini-2.5-flash`.
*   **Process:**
    1.  Constructs a prompt acting as an "expert linguist".
    2.  Requests "Meaning" and "Example Usage".
    3.  Fetches the generated response.
*   **Result:** A rich, context-aware explanation is displayed alongside the static definition.



---

## 🛠 Tech Stack

*   **Frontend:** React (Vite), TypeScript, Tailwind CSS
*   **Data Processing:** Python (`pdfplumber`, `re`)
*   **AI/NLP:** Google Gemini API (`@google/genai`), Web Speech API
*   **Data Storage:** Local JSON files

---

Live Demo Link : https://kokborok-lexlator.vercel.app
