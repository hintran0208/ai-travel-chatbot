# TravelBot - AI Travel Assistant

A sophisticated travel chatbot built with OpenAI SDK, featuring real-time chat, function calling, and external API integrations for comprehensive travel planning assistance.

## 🌟 Features

### Core Capabilities

- **🏨 Hotel Search**: Find and compare hotels with pricing, ratings, and amenities
- **✈️ Flight Search**: Search flights with multiple options for different dates
- **🌤️ Weather Information**: Get weather forecasts for travel planning
- **🎭 Local Activities**: Discover activities, attractions, and experiences
- **💬 Real-time Chat**: WebSocket-powered instant messaging
- **🔧 Function Calling**: OpenAI function calling for dynamic data retrieval

### Advanced Features

- **Multi-turn Conversations**: Context-aware conversation management
- **Conversation History**: Persistent chat history per session
- **Mock Data Generation**: Realistic travel data simulation
- **Responsive Web UI**: Modern, mobile-friendly interface
- **Connection Management**: Auto-reconnection and status indicators

## 🚀 Technologies Used

- **Backend**: FastAPI + Python
- **AI**: OpenAI SDK with function calling
- **Frontend**: Vanilla JavaScript + WebSockets
- **Styling**: Custom CSS with gradients and animations
- **Data**: Mock APIs simulating real travel services

## 📋 Setup Instructions

### Prerequisites

- Python 3.8+
- OpenAI API key

### Installation

1. **Clone and navigate to the project**:

   ```bash
   cd chatbot_v4
   ```

2. **Create virtual environment (recommended)**:

   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On macOS/Linux
   # or
   .venv\Scripts\activate     # On Windows
   ```

3. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**:
   Copy `.env.example` to `.env` and update with your values:

   ```bash
   cp .env.example .env
   ```

   Edit `.env` file with:

   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   OPENAI_BASE_URL=https://aiportalapi.stu-platform.live/jpe
   OPENAI_MODEL_NAME=GPT-4o-mini
   ```

5. **Run the application**:

   Option A - Using the startup script:

   ```bash
   chmod +x start.sh
   ./start.sh
   ```

   Option B - Direct Python execution:

   ```bash
   python main.py
   ```

6. **Access the chat interface**:
   Open <http://localhost:8000> in your browser

## 📁 Project Structure

```
chatbot_v4/
├── .env                    # Environment variables (create from .env.example)
├── .env.example           # Example environment configuration
├── .gitignore             # Git ignore rules
├── .venv/                 # Virtual environment (created during setup)
├── .vscode/               # VS Code settings
├── API_SETUP_GUIDE.md     # API setup documentation
├── Makefile              # Build commands
├── README.md             # This file
├── main.py               # Main FastAPI application
├── requirements.txt      # Python dependencies
├── start.sh              # Startup script
├── static/               # Static web assets (CSS, JS, images)
└── templates/            # Jinja2 HTML templates
    ├── index.html        # Main chat interface
    └── result.html       # Additional template
```

## 🎯 Usage Examples

### Example Conversations

**Hotel Search**:

```text
User: "Find me a hotel in Paris for next weekend"
TravelBot: 🏨 Searching hotels in Paris...
[Shows hotel options with prices, ratings, amenities]
```

**Flight Search**:

```text
User: "Search flights from New York to Tokyo departing December 15th"
TravelBot: ✈️ Finding flights from New York to Tokyo...
[Shows flight options with airlines, times, prices]
```

**Weather Check**:

```text
User: "What's the weather like in London next week?"
TravelBot: 🌤️ Checking weather for London...
[Shows weather forecast with temperatures and conditions]
```

**Activity Suggestions**:

```text
User: "Suggest activities in Barcelona"
TravelBot: 🎭 Looking up activities in Barcelona...
[Shows cultural, adventure, and food activities]
```

## 🔧 API Endpoints

### WebSocket

- `ws://localhost:8000/ws/{conversation_id}` - Real-time chat

### REST API

- `POST /api/chat` - Send chat message
- `GET /api/conversation/{conversation_id}` - Get conversation history
- `DELETE /api/conversation/{conversation_id}` - Clear conversation
- `GET /health` - Health check

### Function Calling

The chatbot uses OpenAI's function calling feature with these functions:

1. **search_hotels(destination, check_in, check_out, guests)**
2. **search_flights(origin, destination, departure_date, return_date)**
3. **get_weather(city, date)**
4. **get_local_activities(destination, activity_type)**

## 🎨 Architecture

### Backend Structure

```text
main.py                 # Main FastAPI application
├── Function Definitions # OpenAI function schemas
├── Mock APIs           # Simulated travel services
├── WebSocket Handler   # Real-time chat management
├── Conversation Manager # Chat history and context
└── REST Endpoints      # API interfaces
```

### Frontend Structure

```text
templates/index.html    # Chat interface
├── TravelChatbot Class # Main chat logic
├── WebSocket Client    # Real-time communication
├── Message Formatting  # Markdown rendering
└── UI Components       # Chat bubbles, indicators
```

## 🌐 Workshop Context

This project addresses the **Workshop 2** objective of building real-world chatbot systems using Azure OpenAI API. It demonstrates:

- **Multi-turn Conversation Management**
- **Function Calling for External APIs**
- **Mock Data Generation**
- **Sophisticated Prompting Techniques**
- **Real-time Chat Interface**
- **Context-aware Responses**

### Problem Solved

The chatbot addresses the real-life challenge of **travel planning complexity** by providing a single interface for:

- Hotel booking assistance
- Flight search and comparison
- Weather-based travel planning
- Local activity discovery
- Comprehensive itinerary planning

## 🚀 Getting Started

1. **Quick Start**:

   ```bash
   python main.py
   ```

2. **Try these prompts**:
   - "Plan a 3-day trip to Rome"
   - "Find me a hotel in Paris for next weekend"
   - "Search flights from New York to Tokyo"
   - "What's the weather like in London?"
   - "Suggest cultural activities in Barcelona"

## 📝 Development Notes

- Mock APIs simulate realistic travel data with random pricing and availability
- Function calling enables dynamic data retrieval based on user queries
- WebSocket implementation provides real-time chat experience
- Conversation context is maintained across multiple exchanges
- Error handling and reconnection logic ensure robust user experience

### Important Notes

- The project includes a `.env.example` file - copy this to `.env` and add your API keys
- The `start.sh` script provides an easy way to launch the application
- **Note**: The `Makefile` currently contains outdated references and may need updating for this travel chatbot project

## 🛠️ Development Setup

For development, you may want to install additional tools:

```bash
# Install development dependencies (optional)
pip install black flake8 pytest

# Format code
black main.py

# Run linting
flake8 main.py
```

## 🔮 Future Enhancements

- Integration with real travel APIs (Booking.com, Expedia, etc.)
- User authentication and profile management
- Booking confirmation and itinerary saving
- Multi-language support
- Voice interface integration
- Trip budget tracking and recommendations
