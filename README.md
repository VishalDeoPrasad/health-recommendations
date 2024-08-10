# AI Internship Assignment: Health Recommendations Based on Blood Test Report

This project implements a pipeline using the CrewAI framework to analyze a blood test report, search for relevant health articles, and provide tailored health recommendations. The goal is to create an intelligent system that automates the process of understanding and responding to blood test results.

## Approach

### 1. **Understanding the Task**
   - **Input**: The system takes a sample blood test report as input.
   - **Analysis**: The report is analyzed to summarize the health data in an easy-to-understand format.
   - **Find Articles**: The system searches the web for articles related to the health needs identified in the blood test.
   - **Recommendations**: Finally, the system provides health recommendations based on the articles found.

### 2. **Implementation Steps**
   - **PDF Text Extraction**: The `PyPDF2` library is used to extract text from specific pages of a blood test report PDF.
   - **Agent Setup**: Three agents are defined using the CrewAI framework:
     - **Blood Test Analyst**: Specializes in summarizing the blood test results.
     - **Article Researcher**: Searches for relevant health articles based on the analysis.
     - **Health Advisor**: Provides health recommendations using the articles found.
   - **Task Definition and Execution**: Each agent is assigned a specific task, and these tasks are orchestrated in sequence using a `Crew` object.

### 3. **Execution Flow**
   - The blood test report is analyzed first.
   - The analysis results are used to search for relevant articles.
   - Health recommendations are provided based on the articles.

## Easy Steps to Run the Code

### 1. **Prerequisites**
   - Ensure the following Python packages are installed:
     ```bash
     pip install PyPDF2 crewai crewai_tools
     ```

### 2. **API Key Setup**
   - Set up your environment variables with the required API keys:
     ```python
     os.environ["SERPER_API_KEY"] = "<your-serper-api-key>"
     os.environ["OPENAI_API_KEY"] = "<your-openai-api-key>"
     ```

### 3. **Update the PDF Path**
   - Modify the `pdf` variable in the script to point to the location of your blood report PDF file. Update `pages_to_extract` to specify the pages to be analyzed.

   ```python
   pdf = 'path_to_your_pdf/blood_report.pdf'
   pages_to_extract = [1, 3]  # Pages to be analyzed
   ```

### 4. **Run the Script**
Execute the script to start the pipeline:
    ```
    python health_recommendations.ipynb
    ```

### 5. **View the Results**
The system will output:
- A summary of the blood test report.
- A list of relevant health articles with links.
- Health recommendations based on the articles.
