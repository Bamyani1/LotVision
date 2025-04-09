# LOTVISION: AI-powered Parking Lot Management System

## Overview
LOTVISION is a comprehensive parking lot management solution that leverages artificial intelligence to monitor vehicle entries and exits, detect unauthorized vehicles, and flag suspicious activity patterns. The system combines computer vision for license plate recognition with advanced AI analysis to provide real-time monitoring and security enhancement for parking facilities.

## Architecture

### Frontend
- **Framework**: React with TailwindCSS
- **Features**: Dashboard for vehicle logs, alert visualization, and system management
- **Directory**: `/frontend`

### Backend
- **Framework**: FastAPI (Python)
- **Database**: SQLite with SQLAlchemy ORM
- **API Endpoints**: Vehicle registration, lot management, current vehicles, flagged vehicles
- **Directory**: `/backend`

### AI Components
- **License Plate Recognition**: OpenCV + PaddleOCR
- **Suspicious Activity Analysis**: Google Gemini AI
- **Directory**: `/camera`

## Setup & Installation

### Prerequisites
- Python 3.8+ for backend and ML components
- Node.js and npm for frontend
- Google Gemini API key

### Backend Setup (FastAPI)

1. **Clone the repository**
   ```sh
   git clone https://github.com/Bamyani1/LotVision.git
   cd lotvision
   ```

2. **Install dependencies**
   ```sh
   cd backend
   python -m venv venv
   source venv/bin/activate  # On Unix/MacOS
   # or
   venv\Scripts\activate  # On Windows
   pip install -r requirements.txt
   ```

3. **Configure environment variables**
   Create a `.env` file in the `/backend` directory:
   ```
   DATABASE_URL=your-sqlite-db
   GEMINI_API_KEY=your-google-gemini-api-key
   FRONTEND_URL=http://localhost:3000
   SECRET_KEY=your-secret-key-for-sessions
   ```

4. **Run the FastAPI server**
   ```sh
   python main.py
   ```
   The API will be available at `http://127.0.0.1:8000`

### Frontend Setup (React + TailwindCSS)

1. **Install dependencies**
   ```sh
   cd ../frontend
   npm install
   ```

2. **Configure environment variables**
   Create a `.env` file in the `/frontend` directory:
   ```
   REACT_APP_BACKEND_URL=http://127.0.0.1:8000
   REACT_APP_GEMINI_API_KEY=your-google-gemini-api-key
   ```

3. **Start the development server**
   ```sh
   npm run start
   ```
   The React application will be available at `http://localhost:3000`

### License Plate Recognition Module

1. **Install dependencies**
   ```sh
   cd ../camera
   pip install -r requirements.txt
   ```
   
   Key dependencies:
   - opencv-python (≥ 4.8.0)
   - numpy (≥ 1.24.0)
   - torch (≥ 2.0.0)
   - easyocr (≥ 1.7.1)
   - paddleocr (≥ 2.9.0)

2. **Run the license plate detector**
   ```sh
   python "number_plate 7.py"
   ```

## Technical Components

### Database Models
- **Registered Cars**: Approved vehicles with associated metadata
- **Parking Lots**: Defined parking areas with capacity information
- **Current Cars**: Vehicles currently in the parking lot
- **Flagged Cars**: Unauthorized or suspicious vehicles

### API Routes
- `/registered_cars`: Management of authorized vehicles
- `/lots`: Parking lot configuration and status
- `/current_cars`: Currently parked vehicles tracking
- `/flagged_cars`: Handling of suspicious or unauthorized entries

### License Plate Recognition Pipeline
1. Video frame capture using OpenCV
2. Region of interest detection
3. Text extraction via PaddleOCR
4. License plate validation and formatting
5. Backend API integration for vehicle processing

### AI Analysis
The system utilizes Google Gemini AI to analyze vehicle entry patterns and flag suspicious activity based on:
- Unusual entry/exit times
- Frequency of appearances
- Comparison against authorized vehicle database

## Features

- **Vehicle Entry & Exit Logging**: Comprehensive tracking of all vehicles
- **Unauthorized Vehicle Detection**: Identification of vehicles not in the approved database
- **Suspicious Activity Analysis**: AI-powered detection of unusual behaviors
- **Real-time Monitoring**: Dashboard visualization of current parking lot state
- **Alert System**: Notifications for security personnel about suspicious vehicles

## Future Improvements

- **User Authentication**: Role-based access control for system administrators
- **Mobile Application**: Companion app for security personnel
- **Integration with Barrier Systems**: Automated gate control
- **Advanced Analytics**: Historical data analysis and trend identification
- **Automated Alerts**: SMS or email notifications for security events

## Contributors

- **Inesh Tickoo**
- **Mostafa Anwari**
- **Nick Davis**

## Contributing

Contributions to the LOTVISION project are welcome. Please follow these steps:

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a pull request

## License

This project is proprietary and not open for redistribution without explicit permission.

