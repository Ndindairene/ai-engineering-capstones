### 6. Privacy and Compliance

The system includes these initial safeguards:

- Contact-information masking before model access
- No automatic restoration of masked details
- Input validation in calculation tools
- Instructions against unsupported diagnoses
- Escalation instructions for emergency concerns
- Separation of API keys from source code
- Fictional rather than real patient information

Limitations:

- Regex masking does not detect every form of PII.
- Retrieved documents are not inherently trustworthy.
- The current system does not prove compliance with
  Kenya's Data Protection Act, 2019.
- Production deployment would require additional
  authorization, access controls, auditing, and testing.

### 7. Installation

Prerequisites:

- Python 3.12
- A compatible Python virtual environment
- An OpenRouter API key

Install dependencies:

    python -m pip install -r requirements.txt

Copy .env.example to .env and configure:

    OPENROUTER_API_KEY=your_key_here
    MODEL_BASE_URL=https://openrouter.ai/api/v1

Never commit real API keys.

### 8. Running the Application

From the Week2_Capstone directory:

    python -m src.main

Example questions:

1. Does diagnostic imaging require prior authorization?
2. Which department handles that authorization?
3. Calculate BMI for 70 kg and 170 cm.

Type exit to close the application.

### 9. Automated Testing

Privacy tests:

    python -m pytest tests/test_privacy.py -v

RAG tests:

    python -m pytest tests/test_rag.py -v

Calculation tool tests:

    python -m pytest tests/test_tools.py -v

Live end-to-end tests:

    python -m pytest tests/test_end_to_end.py -v

Run all tests:

    python -m pytest tests/ -v

The end-to-end tests use the real OpenRouter API and
may incur usage charges.

### 10. Evaluation

Verified during development:

- Privacy masking: 9 initial tests passed
- RAG retrieval: live retrieval test passed
- LangChain RAG tool: successfully executed
- Live end-to-end tests: 3 passed

These results are development checks, not a formal
clinical safety or security certification.

### 11. Git Workflow

Required feature branch:

    feat-rag-agent-system

The completed capstone should be submitted through
a GitHub pull request into main, followed by review
and merge.

### 12. Future Improvements

- Persistent vector database
- Stronger PII detection and redaction
- Streaming-specific privacy validation
- Retrieval relevance and groundedness evaluation
- Request authorization and audit logging
- More comprehensive error handling
- Production-grade monitoring

### 13. Conclusion

AfyaPlus demonstrates how AI engineering components
can be combined into a document-grounded assistant
with tool calling, conversation memory, and initial
privacy safeguards.

The project is an educational prototype intended
to demonstrate Week 2 Applied AI Engineering skills.