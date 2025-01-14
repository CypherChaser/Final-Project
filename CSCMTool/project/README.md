Project Workflow

This project includes two core functionalities: Promotion AI and Customer Support AI, both integrated with a futuristic and space-themed design. Below is the detailed workflow for each functionality:



1. Promotion AI Workflow
Objective:

To deliver personalized promotional messages to individual customers based on their names and targeted campaigns.

Workflow:

Frontend Interaction:
The user provides input (e.g., customer name, product, discount offer) through the space-themed web interface.
The data is sent to the backend using a POST request.
Backend Processing:
The backend uses the provided customer name and promotional details to dynamically create a personalized promotional message using OpenAI’s GPT model.
Example:
Input: { name: "John", product: "Smartphone X", offer: "20% off", link: "https://example.com" }
Generated Message: "Hi John! We're thrilled to offer you an exclusive 20% discount on Smartphone X. Don't miss out! Visit https://example.com to grab your deal."
Output:
The generated message is returned to the frontend and displayed in the UI.
Optionally, the promotion can also be converted to speech and played as audio using the Text-to-Speech (TTS) feature.



2. Customer Support AI Workflow
Objective:

To assist customers by answering queries and providing order-related details.

Workflow:

Frontend Interaction:
The user speaks or types their query in the space-themed web interface.
For order-related queries, they provide their name and order ID.
The input is sent to the backend using a POST request.
Backend Processing:
The backend matches the user’s query with predefined intents (e.g., general support or order details).
For general queries:
The AI generates a response using the system prompt designed for customer service.
For order-related queries:
The backend retrieves order information (stored in a orders.json file).
If the order is found, the details are included in the AI response.
If not, the AI apologizes and asks the user to check their order ID.
Output:
The AI-generated response is returned to the frontend and displayed as text.
For enhanced accessibility, the response is also converted to audio and played back to the user.




3. General Workflow
a. Speech-to-Text Integration (Optional):

For user queries spoken via the microphone, the Web Speech API is used to convert speech into text on the frontend.
The text query is sent to the backend for further processing.
b. Text-to-Speech Integration:

Both the promotional messages and customer support responses are optionally converted into speech using TTS (e.g., OpenAI or another TTS API).
The audio is returned as a Base64-encoded string and played on the frontend.
c. Order Management:

Orders are stored and retrieved from a JSON file (orders.json).
New orders can be added dynamically through the API.
