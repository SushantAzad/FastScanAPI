# FastScanAPI

## Overview

FastScanAPI is a FastAPI-based web service that integrates with Burp Suite to automate security scanning of URLs. It extracts URLs from user queries, determines whether a scan is needed, and initiates the scan via Burp Suite's API.

## Features

-  Extracts target URLs from user queries.

-  Initiates security scans using Burp Suite.

- Returns scan ID upon successful scan initiation.

- Built with FastAPI for fast and efficient performance.
## Requirements

- Python 3.8+

- FastAPI

- Requests

- dotenv

- Burp Suite (with API enabled)

- curl (for testing API endpoints)

## Installation

- Clone the repository:  
   ```
   git clone https://github.com/yourusername/FastScanAPI.git
   cd FastScanAPI 
   ```

- Install dependencies:
   ```
   pip install -r requirements.txt
   ```
- Set up environment variables:

   - Create a .env file in the project root.
   - Add your OpenAI API key (if used in enhancements) and Burp Suite API URL:
   ```
   OPENAI_KEY=your_openai_api_key
   ```
## Usage

- Start the FastAPI server:
   ```
   uvicorn main:app --host 0.0.0.0 --port 8000
   ```
- Make a scan request using cURL:
   ```
   curl -X POST "http://localhost:8000/scan" -H "Content-Type: application/json" -d '{"query": "Scan https://example.com"}'
   ```
- Expected Response:
   ```
   {
      "status": "Scan started!",
      "scan_id": "abcd1234-5678-efgh-ijkl-9876mnopqrst"
   }
   ```
## API Endpoints

### Scan Endpoint

POST /scan
- Request Body:
   ``` 
   {
      "query": "Scan https://example.com"
   }
   ```
- Response:
   ``` 
   {
      "status": "Scan started!",
      "scan_id": "abcd1234-5678-efgh-ijkl-9876mnopqrst"
   }
   ```
## Troubleshooting

- Ensure Burp Suite is running and the API is enabled.

- Check if the Burp API URL is correct and accessible.

- Verify dependencies are installed properly.
