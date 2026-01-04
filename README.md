
#  AI Physician Notetaker & Analyzer

**Candidate Submission for Emitrr Inc. AI Intern Role**

This project demonstrates a modular AI pipeline designed to automate medical documentation. It processes physician-patient conversations to extract clinical entities, analyze patient sentiment, and generate structured SOAP notes.

##  Project Structure

- `physician_notetaker.ipynb`: The main Jupyter Notebook containing the end-to-end pipeline, code logic, and interview question answers.

##  Key Features

### 1. Medical NLP Summarization (NER)
- Extracts key clinical details including Patient Name, Symptoms, Diagnosis, Treatments, and Prognosis.
- Utilizes a hybrid approach combining Spacy for linguistic structure and rule-based logic for high-precision medical entity extraction.

### 2. Sentiment & Intent Analysis
- Analyzes patient dialogue to detect emotional states (Anxious, Neutral, Reassured).
- Identifies patient intent (e.g., "Seeking reassurance", "Reporting symptoms") using Zero-Shot Transformer models.

### 3. Automated SOAP Note Generation
- Converts raw transcripts into the standard clinical format:
  - **Subjective** (Patient's view)
  - **Objective** (Physical findings)
  - **Assessment** (Diagnosis)
  - **Plan** (Treatment & Follow-up)

##  Setup & Usage

### Prerequisites
- Python 3.8+
- Jupyter Notebook / Google Colab

### Installation

Run the following commands to install the necessary dependencies:

\`\`\`bash
pip install spacy transformers torch pandas
python -m spacy download en_core_web_sm
\`\`\`

### Running the Project

1. Open \`physician_notetaker.ipynb\` in Jupyter Notebook or VS Code.
2. Run the cells sequentially:
   - **Step 1-3**: Installs dependencies and initializes the \`ScribeEngine\` class.
   - **Step 4**: Loads the sample transcript.
   - **Tasks 1-3**: Executes the NLP pipeline and displays the JSON outputs.
3. **Q&A**: Refer to the markdown cells following each task for detailed answers to the assignment's theoretical questions.

##  Model Architecture

- **NER Engine**: Spacy (\`en_core_web_sm\`) + Clinical Regex Patterns
- **Sentiment Classifier**: HuggingFace Transformers (\`valhalla/distilbart-mnli-12-3\`) for Zero-Shot Classification
- **Logic Layer**: Custom Python class (\`ScribeEngine\`) handling data mapping and JSON structuring
