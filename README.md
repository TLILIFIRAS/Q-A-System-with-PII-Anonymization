Question-answering system with PII anonymization
================================================

This project implements a document anonymization and query system that leverages the capabilities of LangChain and OpenAI's language models. The system is designed to anonymize sensitive information in documents, enabling secure and privacy-preserving querying.

Features
--------

*   **Anonymization**: Sensitive information such as names, dates, and personal identifiers are anonymized using the Presidio framework.
    
*   **Contextual Querying**: Users can ask questions based on anonymized documents, and the system retrieves relevant context while respecting privacy.
    
*   **Integration with OpenAI**: The project uses OpenAI's language models to generate answers based on the provided context.
    
*   **Flexible Architecture**: The system is built using LangChain, allowing for easy customization and extension.
    

Getting Started
---------------

### Prerequisites

*   Python 3.7 or higher
    
*   Access to OpenAI API (API key required)
    
*   Required Python libraries
    

### Installation

Clone this repository:

`   git clone https://github.com/TLILIFIRAS/Q-A-System-with-PII-Anonymization.git   `

Install the required dependencies:

`   pip install -r requirements.txt   `

Set your OpenAI API key:

You can set the API key as an environment variable:

`   export OPENAI_API_KEY="your_openai_api_key"   `

Alternatively, you can specify the API key directly in the code (not recommended for production).Usage

### Load your documents and create instances of the necessary classes:

Load your documents and create instances of the necessary classes:

`langchain_core.documents import Document
from langchain_experimental.data_anonymizer import PresidioReversibleAnonymizer  
from langchain_openai import ChatOpenAI  # Initialize your anonymizer and model  
anonymizer = PresidioReversibleAnonymizer()  
model = ChatOpenAI(temperature=0.3)  # Load your documents  
documents = [Document(page_content="Your document content here.")]   `

### Anonymize the documents:

` for doc in documents:      doc.page_content = anonymizer.anonymize(doc.page_content)   `

### Retrieve answers based on your queries:

L`   answer = anonymizer_chain.invoke({"question": "What happened on ?"})  print(answer)   `

License
-------

This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgments
---------------

*   LangChain - for providing the framework for building LLM applications.
    
*   OpenAI - for the powerful language models that enable intelligent querying.
    
*   Presidio - for the anonymization capabilities.
    

Contributing
------------

Contributions are welcome! Please feel free to submit a Pull Request.

Contact
-------

For any inquiries, please get in touch with me at in/firastlili
