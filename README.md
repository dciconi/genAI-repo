# **Project Repository: AI Generation and Quality Control**

Welcome to the project repository dedicated to genAI - an autonomous system that take a Common Core learning standard and a topic of student interest and generate customized free-response questions that test the student’s knowledge.

genAI’s primary function is to autonomously generate educational content based on the Common Core State Standards (CCSS) for English Language Arts (ELA) and to evaluate student answers. This is achieved by interfacing with OpenAI’s GPT model.

**Tasks genAI will complete:**

1. **Question Generation**: Generate a free-response question aligned with a specific learning standard and interest topic.
2. **Rubric Creation**: Construct a rubric for evaluating answers to the produced question.
3. **Answer Evaluation**: Assess a given student's answer based on the rubric and provide feedback.

**Inputs Required:**

1. **Common Core State Standards**: A CSV file ('ela-ccss.csv') containing the English Language Arts standards. Each standard has a unique identifier and its description.
2. **Learning Standard ID**: E.g., 'CCSS.ELA-LITERACY.W.4.9'
3. **Interest Topic**: E.g., 'tv series'
4. **Student's Answer**: A free-response answer provided by a student to the generated question.

**Expected Outputs:**

1. A context-aware **question** based on the learning standard and interest topic.
2. A **rubric** for evaluating answers to the question.
3. **Feedback** on the student's answer, using the generated rubric.

**Technical Implementation:**

1. **Loading CCSS Data**: The Common Core State Standards for ELA are loaded into a Pandas DataFrame from a CSV file.
2. **OpenAI API Configuration**: The OpenAI API key and model (e.g., gpt-3.5-turbo) are set up.
3. **AI Conversation Interface**: The core function **`chat_with_openai`** serves as an interface to communicate with the GPT model using OpenAI's chat-based API. It accepts a prompt, sends it to the AI, maintains a conversation history, and retrieves the AI's response.
4. **Content Generation Functions**:
    - **`generate_question`**: Uses AI to produce a question.
    - **`generate_rubric`**: Employs AI to create an evaluation rubric.
    - **`evaluate_answer`**: Engages AI to evaluate the student's answer and provide feedback.

**Model Used:**
The prototype will be tested in the **`gpt-3.5-turbo`** model, but it can easily be switched between other OpenAI’s models. This model is chosen because it offers a balance of performance and efficiency. It's particularly suited for tasks that require conversational back-and-forth, making it ideal for this application.