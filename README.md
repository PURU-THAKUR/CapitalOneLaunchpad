# PHASAL MVP - AI-Powered Farming Assistant

## Overview
PHASAL is an AI-powered farming assistant designed specifically for Indian farmers. This MVP demonstrates the core features including multimodal agricultural analysis, conversational AI chatbot, and mandi price intelligence.

## Features

### 1. Multimodal Agricultural Analysis
- **Camera Integration**: Take photos directly from the app
- **Gallery Support**: Select existing photos for analysis
- **AI Analysis**: Mock backend provides analysis for:
  - Crop disease detection
  - Soil health assessment
  - Weather prediction from sky photos

### 2. Conversational AI Chatbot
- **Hindi/English Support**: Bilingual interface
- **Keyword-based Responses**: Responds to queries about:
  - Weather (मौसम)
  - Market prices (मंडी भाव)
  - Government schemes (योजना)
  - Fertilizers (खाद)
  - Crop diseases (रोग)
  - Irrigation (सिंचाई)

### 3. Mandi Price Intelligence
- **Real-time Prices**: Hardcoded data for demonstration
- **Multiple Crops**: Wheat, Rice, Tomato
- **Multiple Markets**: Patna, Darbhanga, Muzaffarpur, etc.

## Technology Stack

### Frontend (Flutter)
- **Framework**: Flutter 3.10+
- **Language**: Dart
- **Key Packages**:
  - `http`: API communication
  - `image_picker`: Camera and gallery access
  - `material_design`: UI components

### Backend (Node.js)
- **Framework**: Express.js
- **Language**: JavaScript
- **Key Packages**:
  - `express`: Web framework
  - `cors`: Cross-origin resource sharing
  - `body-parser`: Request parsing

## Setup Instructions

### Backend Setup
1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the server:
   ```bash
   npm start
   ```
   
   For development with auto-reload:
   ```bash
   npm run dev
   ```

4. The server will run on `http://localhost:3000`

### Frontend Setup
1. Navigate to the Flutter app directory:
   ```bash
   cd flutter_app
   ```

2. Install Flutter dependencies:
   ```bash
   flutter pub get
   ```

3. Update the API base URL in `lib/services/api_service.dart` if needed:
   ```dart
   static const String baseUrl = 'http://localhost:3000';
   ```

4. Run the Flutter app:
   ```bash
   flutter run
   ```

## API Endpoints

### POST /analyze
Analyzes uploaded images based on filename.

**Request Body:**
```json
{
  "filename": "diseased_leaf.jpg"
}
```

**Response Examples:**
- **Crop Disease**: `diseased_leaf.jpg`
- **Soil Analysis**: `soil_sample.jpg`  
- **Weather**: `cloudy_sky.jpg`

### POST /chatbot
Processes chat queries and returns appropriate responses.

**Request Body:**
```json
{
  "query": "मौसम कैसा रहेगा?"
}
```

**Response:**
```json
{
  "response": "अगले 2 दिनों में हल्की बारिश की संभावना है।"
}
```

## Mock Data

### Analysis Responses
The backend provides mock responses for specific filenames:
- `diseased_leaf.jpg` → Crop disease analysis
- `soil_sample.jpg` → Soil health assessment
- `cloudy_sky.jpg` → Weather prediction

### Chatbot Keywords
The chatbot responds to these Hindi/English keywords:
- Weather: `weather`, `मौसम`
- Prices: `price`, `मंडी`, `भाव`
- Schemes: `scheme`, `योजना`
- Fertilizer: `fertilizer`, `खाद`, `उर्वरक`
- Disease: `disease`, `रोग`, `बीमारी`
- Irrigation: `irrigation`, `सिंचाई`, `पानी`

### Mandi Prices
Hardcoded price data for:
- **Wheat**: ₹2150-2200/quintal
- **Rice**: ₹3150-3200/quintal  
- **Tomato**: ₹1450-1600/quintal

## Development Notes

### For Production Deployment
1. **Replace Mock APIs**: Integrate real APIs like:
   - Gemini Vision API for image analysis
   - OpenWeatherMap for weather data
   - eNAM/AgMarkNet for mandi prices

2. **Add Authentication**: Implement Firebase Auth or similar

3. **Database Integration**: Use Firebase Firestore or similar

4. **Real-time Features**: Add WebSocket support for live updates

5. **Offline Support**: Implement local caching with TensorFlow Lite

### Testing
- Test image analysis with different filenames
- Try various chatbot queries in Hindi and English
- Verify mandi price display for all crops

## License
This is a hackathon MVP project. All rights reserved.

## Contact
For questions or support, please contact the development team.
