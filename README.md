# AI Empathy: Personal AI Coach 🤖

AI Empathy is an interactive, AI-powered empathy coach built using Streamlit and LangChain. This application gathers personal details from users through a sidebar and uses an AI-powered conversational chain to offer personalized advice on personal growth, emotional well-being, and career guidance.

---

## Features

- **Conversational Chat Interface:** Chat with an empathetic AI coach that responds to your personal and career-related queries.
- **Personalized User Data:** Enter your name, age, gender, interests, mood, and career details in the sidebar to tailor the conversation.
- **Custom Styling:** Enjoy a modern user interface with a custom-styled input box and a dark-themed look with white text.
- **Contextual Memory:** Uses LangChain’s ConversationBufferMemory to maintain conversation context.
- **Efficient Data Retrieval:** Leverages FAISS with HuggingFace embeddings for efficient data indexing and retrieval.
- **Multiple LLM Options:** Integrated with ChatGroq (or ChatOpenAI, if desired) for generating responses.

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/ai-empathy-personal-ai-coach.git
cd ai-empathy-personal-ai-coach
```

### 2. Create and Activate a Virtual Environment

On **Windows**:
```bash
python -m venv .venv
.venv\Scripts\activate
```

On **macOS/Linux**:
```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

Ensure you have a `requirements.txt` file (include packages such as `streamlit`, `langchain`, `faiss-cpu`, `python-dotenv`, etc.). Then run:

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the project root with your API keys. For example:

```ini
GROQ_API_KEY=your_groq_api_key_here
```

---

## Usage

To run the application, use the following command:

```bash
streamlit run app.py
```

*Note:* Replace `app.py` with your main script filename if it differs.

---

## Project Structure

```
ai-empathy-personal-ai-coach/
├── Ai_empthy.py                    # Main application script
├── htmlTemplates.py          # HTML/CSS templates for chat messages
├── requirements.txt          # List of dependencies
├── .env                      # Environment variables file (not committed)
└── README.md                 # This file
```

---

## Code Overview

- **Main Application (app.py):**  
  Contains the Streamlit code to set up the UI, capture sidebar inputs, and handle conversations with the AI coach.
  
- **Vectorstore and Conversation Chain:**  
  - `get_vectorstore(user_data)` creates a FAISS vectorstore using HuggingFace embeddings.
  - `get_conversation_chain(vectorstore)` initializes a conversational retrieval chain with a custom prompt.
  
- **Custom Styling:**  
  The input box is styled with CSS injected via `st.markdown()`. The styling includes a dark background with white text, rounded borders, and a shadow effect.
  
- **Handling User Input:**  
  The function `handle_userinput(user_question)` processes user queries through the conversation chain and updates the chat history.

---

## Customization

### Changing the Chat Input Appearance

The input box is styled via injected CSS in the main script. For example, to change its background color or border color, modify the CSS block:

```css
.stTextInput {
  position: fixed;
  bottom: 3rem;
  transform: translateX(-50%) !important;
  width: 50% !important;
  padding: 14px !important;
  font-size: 16px !important;
  border: 2px solid #ccc !important;
  border-radius: 25px !important;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1) !important;
  z-index: 9999 !important;
  outline: none !important;
  background-color: #333 !important; /* Dark background */
  color: white !important;
  transition: left 0.3s ease, width 0.3s ease !important;
}
.stTextInput:focus {
  border-color: #0084ff !important;
  box-shadow: 0px 0px 8px rgba(0, 132, 255, 0.6) !important;
}
```

Feel free to modify these values to suit your design preferences.

---

## Acknowledgements

- [Streamlit](https://streamlit.io/)
- [LangChain](https://python.langchain.com/)
- [HuggingFace](https://huggingface.co/)
- [FAISS](https://github.com/facebookresearch/faiss)
- [ChatGroq](https://github.com/your-source) (or ChatOpenAI)

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contributing

Contributions are welcome! Feel free to fork the repository and submit pull requests with improvements or bug fixes.

---

## Contact

For questions or support, please open an issue in the repository or contact [your-email@example.com](mailto:your-email@example.com).

```

---

Feel free to adjust any sections (URLs, contact information, or other details) as needed. This `README.md` provides a complete overview of your project, instructions for installation and usage, and additional information about customization and contribution.
