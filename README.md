# TalentScout Hiring Assistant Chatbot

## Project Overview

TalentScout Hiring Assistant is an AI-powered chatbot designed for TalentScout, a recruitment agency specializing in technology placements. The chatbot streamlines the initial candidate screening process by:

- Gathering essential candidate information through natural conversation
- Analyzing candidates' technical skills and experience
- Generating relevant technical questions based on declared tech stacks
- Providing a consistent and efficient interview experience

This intelligent assistant helps recruiters save time on initial screenings while ensuring candidates are evaluated against appropriate technical standards for their claimed skill sets.

## Capabilities

* **Information Gathering:** Collects candidate details such as name, email, phone, experience, desired position, and location.
* **Tech Stack Analysis:** Analyzes the candidate's self-reported tech stack to identify technologies and proficiency levels.
* **Technical Question Generation:** Dynamically generates relevant technical questions based on the candidate's tech stack and experience.
* **Conversation Management:** Guides the conversation flow through different stages of the interview process.
* **Data Storage:** Saves candidate data and interview responses to JSON files for review by recruiters.

## Installation Instructions

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/Heminoid/Hiring-Assistant-chatbot.git
   cd talentscout-hiring-assistant
   ```

2. **Install Dependencies:**
   ```bash
   pip install gradio openai python-dotenv
   ```

3. **Set Up OpenAI API Key:**
   * Create a `.env` file in the project directory.
   * Add your OpenAI API key to the `.env` file:
     ```
     OPENAI_API_KEY=your_api_key_here
     ```
   * Alternatively, uncomment and modify the line in the code:
     ```python
     # client = OpenAI(api_key="your-api-key-here")
     ```

4. **Run the Application:**
   ```bash
   python app.py
   ```
   
5. **Access the Interface:**
   * Open the URL provided in the terminal.

## Usage Guide

### For Candidates:

1. **Start the Interview:**
   * The chatbot will automatically greet you and explain the process
   * Respond to each question honestly and thoroughly

2. **Information Collection:**
   * You'll be asked for your name, email, phone number, and other basic information
   * For experience level, you can either type your answer or use the radio button selection

3. **Technical Assessment:**
   * List your technical skills when prompted
   * Answer the technical questions to demonstrate your proficiency
   * Questions will increase in difficulty as the interview progresses

4. **End the Interview:**
   * The chatbot will conclude the conversation after three technical questions
   * To end early, type "exit," "quit," "bye," or "goodbye"

### For Recruiters/Administrators:

1. **Accessing Candidate Data:**
   * Interview data is stored in JSON files named `candidate_[UUID].json`
   * Each file contains all candidate information and their responses to technical questions

2. **Reset Functionality:**
   * Click the "Reset Conversation" button to start a new interview session

## Technical Details

### Libraries and Tools
- **Gradio**: Provides the user interface for chatbot interactions
- **OpenAI API**: Powers the conversational intelligence and technical question generation
- **Python-dotenv**: Manages environment variables for API keys
- **Regular Expressions**: Validates email and phone number inputs
- **JSON**: Stores candidate data in a structured format
- **UUID**: Generates unique identifiers for each candidate
- **Datetime**: Records interview timestamps

### Architecture
- **State Machine**: The conversation flows through defined states (greeting, name collection, email, etc.)
- **Error Handling**: Includes input validation, API error recovery, and retry logic
- **Message Context Management**: Maintains conversation history for coherent interactions
- **Two-Column UI Layout**: Separates conversation (right) from controls and information (left)

### Data Privacy
- Candidate data is stored locally in JSON format
- No data is transmitted except to the OpenAI API for processing
- Personal information validation occurs on the client side

## Prompt Design

The prompt engineering in this project was carefully crafted to achieve specific outcomes at each stage of the conversation:

### System Prompt
The system prompt establishes the chatbot's identity and behavioral parameters:
```
You are an AI hiring assistant for TalentScout, a recruitment agency specializing in technology placements.
Your role is to gather essential information from candidates and assess their technical skills.
Be professional, courteous, and focused on the recruitment process.
```

### Stage-Specific Prompts
- **Greeting Prompt**: Introduces the chatbot and explains its purpose
- **Tech Stack Prompt**: Requests comprehensive information about technical skills
- **Technical Questions Prompt**: Generates appropriate questions based on the candidate's tech stack and experience level

### Technical Question Generation
The technical question prompt includes specific guidelines:
- Questions should match the exact technologies mentioned
- Include both knowledge-based and problem-solving questions
- Adjust difficulty based on years of experience
- Include algorithmic challenges for programming languages
- Focus on best practices for frameworks
- Cover optimization for databases

## Challenges & Solutions

### 1. Context Management
**Challenge**: Maintaining conversation context across multiple exchanges.  
**Solution**: Implemented a state machine approach that tracks the conversation stage and maintains a message history for context.

### 2. Input Validation
**Challenge**: Ensuring valid email and phone formats without disrupting conversation flow.  
**Solution**: Used regular expressions for validation with specific error messages that guide users to provide correctly formatted information.

### 3. Error Handling
**Challenge**: API failures could interrupt the interview process.  
**Solution**: Implemented a retry mechanism with exponential backoff, along with fallback responses when the API is unavailable.

### 4. Technical Question Relevance
**Challenge**: Generating questions specifically tailored to the candidate's tech stack.  
**Solution**: Developed a tech stack analysis function that categorizes technologies before generating questions, ensuring relevance.

### 5. UI/UX Design
**Challenge**: Creating an intuitive interface that works across different devices.  
**Solution**: Used Gradio's responsive design capabilities with custom CSS for better message styling and visibility.

## Future Enhancements

- **Sentiment Analysis**: Gauge candidate emotions during the conversation
- **Multilingual Support**: Interact with candidates in different languages
- **Interactive Coding Challenges**: Incorporate real-time coding tests for technical assessment
- **Integration with ATS**: Connect with Applicant Tracking Systems for streamlined recruitment

## Contributing
Contributions are welcome! If you find any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.

## License
This project is licensed under the MIT License.

---

*This project was developed as part of an AI/ML Intern Assignment with a 48-hour deadline, demonstrating prompt engineering capabilities and LLM integration skills.*
