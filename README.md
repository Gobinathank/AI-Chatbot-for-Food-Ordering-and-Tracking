🍕 AI Chatbot: Food Ordering & Tracking
Project Description
An intelligent conversational agent built to streamline the food ordering experience. This system allows users to browse items, place orders, modify carts, and track delivery status in real-time through a natural language interface.

🚀 Project Overview
This system bridges the gap between customer convenience and backend efficiency. By leveraging Dialogflow for Natural Language Understanding (NLU) and FastAPI for a high-performance backend, it provides a seamless end-to-end ordering workflow.

🛠 Tech Stack
NLU / NLP: Dialogflow ES

Backend Framework: FastAPI (Python 3.7+)

Database: MySQL

Tunneling: ngrok (for Webhook integration)

Frontend: HTML5 / CSS3

✨ Key Features
Natural Language Ordering: Simply tell the chatbot what you want (e.g., "Add 2 pizzas and a coke").

Dynamic Cart Management: Add, update, or remove items before final checkout.

Real-time Tracking: Instantly retrieve order status using a unique Order ID.

Persistence: All order data is stored securely in a MySQL database for reliability.

⚙️ System Architecture
User Interface: The user sends a message through the HTML frontend.

NLU Processing: Dialogflow parses the intent and extracts entities (items, quantities).

Webhook Call: Data is sent to the FastAPI backend via an ngrok tunnel.

Backend Logic: main.py processes the request and uses db_helper.py to query MySQL.

Response: The backend returns a confirmation which the chatbot displays to the user.

📂 Project Structure
Plaintext
📁 ai-chatbot-food-ordering-tracking/
│
├── 📁 frontend/
│   └── index.html           # Web interface with embedded chatbot
│
├── 📁 backend/
│   ├── main.py              # FastAPI entry point & routes
│   ├── db_helper.py         # MySQL CRUD operations
│   └── generic_helper.py    # Utility functions
│
├── 📁 sql/
│   └── db_dump.sql          # Database schema and sample data
│
├── README.md                # Project documentation
└── LICENSE                  # MIT License
🛠 Installation & Setup
1. Prerequisites

Python 3.7 or higher

MySQL Server installed and running

An active Dialogflow account and ngrok installed

2. Local Setup

Bash
# Clone the repository
git clone https://github.com/yourusername/ai-chatbot-food-ordering-tracking.git

# Move into the directory
cd ai-chatbot-food-ordering-tracking

# Create and activate virtual environment
python -m venv venv
# Windows: venv\Scripts\activate | Mac/Linux: source venv/bin/activate

# Install dependencies
pip install fastapi mysql-connector-python uvicorn
3. Database & Webhook

Create a MySQL database named track_n_treat.

Run the FastAPI server: uvicorn main:app --reload.

Expose your local server: ngrok http 8000.

Copy the ngrok HTTPS URL and paste it into the Dialogflow Fulfillment settings.

📜 License
This project is licensed under the MIT License.

🤝 Contact
Gobinathan K

📧 gopinathan1154@gmail.com
