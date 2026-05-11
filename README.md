🍕 AI Chatbot for Food Ordering & TrackingAn intelligent conversational agent designed to streamline the food ordering experience. This system allows users to browse items, place orders, modify carts, and track delivery status in real-time through a natural language interface.🚀 OverviewThis project bridges the gap between customer convenience and backend efficiency. By leveraging Dialogflow for Natural Language Understanding (NLU) and FastAPI for a high-performance backend, the system provides a seamless end-to-end ordering workflow.🛠 Tech StackLayerTechnologyNLU / NLPDialogflow ESBackend FrameworkFastAPI (Python 3.7+)DatabaseMySQLTunnelingngrokFrontendHTML5 / CSS3✨ Key FeaturesNatural Language Ordering: Simply tell the chatbot what you want (e.g., "Add 2 pizzas and a coke").Dynamic Cart Management: Add, update, or remove items before final checkout.Real-time Tracking: Instantly retrieve order status using a unique Order ID.Persistence: All order data is stored securely in a MySQL database for reliability.Webhook Integration: Seamless communication between Dialogflow and the FastAPI backend.⚙️ System ArchitectureUser Interface: The user sends a message through the HTML frontend.NLU Processing: Dialogflow parses the intent (e.g., order.add) and extracts entities (item names, quantities).Webhook Call: Dialogflow sends a JSON payload to the FastAPI backend via an ngrok tunnel.Backend Logic: main.py processes the request and uses db_helper.py to query the MySQL database.Response: The backend returns a text response which the chatbot displays to the user.🛠 Installation & Setup1. PrerequisitesPython 3.7 or higherMySQL Server installed and runningAn active Dialogflow accountngrok installed2. Environment SetupBash# Clone the repository
git clone https://github.com/yourusername/ai-chatbot-food-ordering-tracking.git
cd ai-chatbot-food-ordering-tracking

# Create and activate virtual environment
python -m venv venv
# On Windows: venv\Scripts\activate | On Mac/Linux: source venv/bin/activate

# Install dependencies
pip install fastapi mysql-connector-python uvicorn
3. Database ConfigurationCreate a MySQL database named track_n_treat.Execute the scripts found in the /sql folder to set up the necessary tables.Update your database credentials in backend/db_helper.py:Python# Example configuration
db_config = {
    "user": "root",
    "password": "yourpassword",
    "host": "localhost",
    "database": "track_n_treat"
}
4. Running the ApplicationStart Backend:Bashuvicorn main:app --reload
Start ngrok Tunnel:Bashngrok http 8000
Dialogflow Setup:Copy the https URL from ngrok.In Dialogflow Console, go to Fulfillment > Webhook > Paste the URL + /webhook.Enable Webhook for your intents.📂 Project StructurePlaintext📁 ai-chatbot-food-ordering-tracking/
├── 📁 frontend/
│   └── index.html           # Web interface with embedded chatbot
├── 📁 backend/
│   ├── main.py              # FastAPI entry point & routes
│   ├── db_helper.py         # MySQL CRUD operations
│   └── generic_helper.py    # Regex & string parsing utilities
├── 📁 sql/
│   └── db_dump.sql          # Database schema and sample data
├── README.md                # Project documentation
└── LICENSE                  # MIT License
📜 LicenseThis project is licensed under the MIT License. Feel free to use, modify, and distribute as you see fit. See the LICENSE file for more details.🤝 ContactGobinathan K📧 gopinathan1154@gmail.com🔗 GitHub Profile
