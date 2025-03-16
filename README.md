# TalentScout Hiring Assistant Chatbot

## Project Overview

This project implements an AI-powered hiring assistant chatbot designed to streamline the recruitment process for technology placements. The chatbot interacts with candidates, gathers essential information, assesses their technical skills, and provides a structured interview experience. It leverages the OpenAI API for natural language processing and Gradio for creating a user-friendly interface.

## Capabilities

* **Information Gathering:** Collects candidate details such as name, email, phone, experience, desired position, and location.
* **Tech Stack Analysis:** Analyzes the candidate's self-reported tech stack to identify technologies and proficiency levels.
* **Technical Question Generation:** Dynamically generates relevant technical questions based on the candidate's tech stack and experience.
* **Conversation Management:** Guides the conversation flow through different stages of the interview process.
* **Data Storage:** Saves candidate data and interview responses to JSON files for review by recruiters.

## Installation Instructions

1. **Clone the Repository:**
2. **Navigate to the Project Directory:**
3. **Install Dependencies:**
4. **Set Up OpenAI API Key:**
    * Create a `.env` file in the project directory.
    * Add your OpenAI API key to the `.env` file:
5. **Run the Application:**
## Usage Guide

1. **Access the Chatbot:** Open the provided URL in your web browser after running the application.
2. **Start the Conversation:** The chatbot will greet you and ask for your full name.
3. **Follow the Prompts:** Respond to the chatbot's questions, providing accurate and relevant information.
4. **Technical Assessment:** Answer the technical questions to the best of your ability.
5. **Conversation End:** The chatbot will conclude the interview and inform you about the next steps.

## Technical Details

* **Libraries:**
    * `gradio`: For building the user interface.
    * `openai`: For interacting with the OpenAI API.
    * `python-dotenv`: For loading environment variables.
    * `json`: For data handling.
    * `datetime`: For timestamping interview data.
    * `uuid`: For generating unique candidate IDs.
    * `time`: For pausing between retries.
    * `re`: For regular expression for input validation.
* **Model:** `gpt-3.5-turbo` (or other compatible OpenAI models).
* **Architecture:** The chatbot is implemented as a state machine, transitioning through different conversation stages based on user input.

## Prompt Design

* **System Prompt:** Sets the overall behavior and guidelines for the chatbot.
* **Stage-Specific Prompts:** Guide the chatbot's responses and questions for each conversation stage (greeting, information gathering, tech stack, technical questions, conclusion).
* **Dynamic Prompts:** Technical questions are generated dynamically using prompts that incorporate the candidate's tech stack and experience.

## Challenges & Solutions

* **Handling Unexpected Input:** Implemented input validation and reprompts to guide users towards providing the correct information.
* **Maintaining Context:** Used a message history to provide context to the OpenAI API for generating relevant responses.
* **Generating Effective Technical Questions:** Carefully crafted prompts to ensure technical questions are specific, challenging, and appropriate for the candidate's experience level.


## Contributing
Contributions are welcome! If you find any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.

## License
This project is licensed under the MIT License.
