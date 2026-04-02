# Sky Travel App

Travel App is a travel web application with a static HTML/CSS/JS frontend and a Flask backend. It includes trip planning, destination exploration, guide booking, translation tools, admin workflows, and payment-related booking flows.

## Tech Stack

- Frontend: HTML, CSS, JavaScript
- Backend: Python, Flask, Flask-CORS
- Database: MySQL
- AI and APIs: Google Gemini, Amadeus, OpenWeather, Unsplash, Pexels, Spoonacular, OpenTripMap, LocationIQ
- Other integrations: Razorpay, gTTS, Tesseract OCR, Pillow

## Project Structure

```text
sky-2-30/
├── assets/                  # Images, uploads, generated invoices
├── backend/
│   ├── app.py               # Main Flask app
│   ├── admin.py             # Admin routes
│   ├── explore.py           # Explore and destination data routes
│   ├── guide.py             # Guide registration and booking routes
│   ├── travel.py            # Trip planning and travel routes
│   ├── db.py                # MySQL connection
│   ├── database_schema.sql  # Database schema
│   ├── .env.example         # Safe environment template
│   └── gemini_cache.json    # Cached AI/explore data
├── destination/             # Destination detail pages
├── index.html               # Main frontend entry
└── requirements.txt         # Python dependencies
```

## Main Features

- User registration and login
- Password reset with OTP email flow
- Destination exploration with cached travel content
- Travel planning and trip saving
- Guide registration and public guide listing
- Guide booking, payment flow, refunds, and booking status tracking
- Guide availability management
- Guide ratings and reviews
- Admin views for users, guides, bookings, and reports
- Text, image, and audio translation endpoints
- Booking PDF generation

## Prerequisites

- Python 3.11+
- MySQL
- Tesseract OCR installed on your machine for image text extraction

## Setup

### 1. Install dependencies

```powershell
pip install -r requirements.txt
```

### 2. Create the database

Create a MySQL database named `ai_trip_planner`.

Then import the schema:

```sql
SOURCE backend/database_schema.sql;
```

Or open `backend/database_schema.sql` in MySQL Workbench and run it.

### 3. Configure environment variables

Copy the example file and fill in your real values:

```powershell
Copy-Item backend/.env.example backend/.env
```

Keys commonly used by this project include:

- `GEMINI_API_KEY`
- `GEMINI_TRANSLATE_API_KEY`
- `GEMINI_API_AI_KEY`
- `UNSPLASH_ACCESS_KEY`
- `PEXELS_API_KEY`
- `OPENWEATHER_API_KEY`
- `LOCATIONIQ_KEY`
- `OPENTRIP_API_KEY`
- `SPOONACULAR_API_KEY`
- `AMADEUS_API_KEY`
- `AMADEUS_API_SECRET`
- `RAZORPAY_KEY_ID`
- `RAZORPAY_KEY_SECRET`
- `EMAIL_USER`
- `EMAIL_PASS`
- `DB_HOST`
- `DB_USER`
- `DB_PASSWORD`
- `DB_NAME`

## Running the Project

### Start the backend

From the project root:

```powershell
python backend/app.py
```

The Flask app runs in debug mode by default.

### Open the frontend

Open [index.html](/c:/Users/hp/Desktop/sky-2-30/index.html) in your browser, or run it with a local static server such as VS Code Live Server.

## Important Notes

- This repo uses static frontend pages, so there is no Node or npm setup required.
- The backend currently loads environment values in multiple modules, so make sure `backend/.env` exists before running the server.
- `backend/db.py` currently contains a direct MySQL connection definition. Keep your actual values in `backend/.env` and avoid committing secrets.
- `pytesseract` requires the Tesseract application itself to be installed, not just the Python package.



