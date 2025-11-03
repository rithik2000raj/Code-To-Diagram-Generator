# Code-to-Diagram Generator

The Code-to-Diagram Generator is an AI-assisted developer tool designed to automatically convert source code into visual representations such as UML Class Diagrams, Flowcharts, and Sequence Diagrams. This tool accelerates understanding, documentation, and onboarding for complex codebases by combining static parsing with LLM-based semantic interpretation and programmatic rendering.

The application is built as a modular Python pipeline utilizing Streamlit for the user interface, Graphviz for diagram rendering, and the Groq API for AI-driven analysis and summarization.

**Key Features**

**Multi-Language Parsing:** Support for Python (.py), Java (.java), and Jupyter Notebooks (.ipynb) using AST extraction.

**Static Analysis:** Automatically detects and maps structural relationships, including class hierarchy, method-to-method call graphs, and external dependencies.

**AI Interpretation (LLM):** Integrates with Groq to provide concise, natural-language explanations of complex diagrams, architecture patterns, and answers user queries about the code structure.

**Live Editing & Preview:** Allows users to edit the generated Graphviz (DOT) source code directly and instantly preview the changes.

**Multiple Export Formats:** Export diagrams in ready-to-use formats including PNG, SVG, Markdown (.md) (with embedded image and source), and the raw DOT source code.

# Architecture Overview

The system operates as an end-to-end pipeline:

**Ingestion & Parsing (parser_module.py):** Accepts code, builds the Abstract Syntax Tree (AST), and extracts raw structural components (classes, functions, methods, calls).

**Analysis (analyzer.py):** Performs deep static analysis to map relationships, calculate complexity metrics, and generate call graph edges.

**Diagram Generation (diagram_generator.py):** Converts the analyzed structure into a Graphviz DOT definition.

**UI & LLM Integration (app.py, llm_integration.py):** The Streamlit app displays the diagram, uses the LLM to explain the results, and handles user queries.

**Rendering & Export (exporter.py):** Renders the final DOT definition into the requested image and documentation formats.

# Prerequisites

To run this project, you need:

Python 3.8+

**Graphviz Binaries:** The Graphviz software must be installed on your system and accessible via your system's PATH variable for image rendering to function.

**Groq API Key:** Required for all AI-assisted features (explanations, chat queries).

**Installation and Setup**

**1. Clone the repository**

git clone [YOUR_REPOSITORY_URL]
cd code-to-diagram-generator


**2. Install Python Dependencies**

Install the required libraries using pip:

pip install -r requirements.txt


**3. Configure API Key**

Create a file named .env in the root directory and add your Groq API key:

GROQ_API_KEY="YOUR_GROQ_API_KEY_HERE"


**Usage**

Start the Streamlit application from your terminal:

streamlit run app.py


The application will open in your default web browser.

**Upload Code:** Use the file uploader to submit a .py, .java, or .ipynb file.

**View Analysis:** Review the structural summary and the generated diagram on the Main Analysis page.

**Query Code:** Navigate to the Code Queries page to ask the AI questions about the code structure and relationships.

**Export:** Use the export section to download the diagram in various formats.

