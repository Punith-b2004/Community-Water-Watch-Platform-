Community Water Watch
Overview
Community Water Watch is an innovative platform designed to monitor and report water cleanliness issues in local communities. By leveraging AI-powered image analysis, blockchain for secure data logging, and a user-friendly web interface, this project empowers citizens to report littered water bodies, enabling authorities to take action. The system uses machine learning to classify reports as "Clean" or "Littered," stores verified data on a blockchain, and provides a dashboard for users and officials to track reports.
Problem Statement
Water pollution is a critical issue affecting ecosystems and public health. Many communities lack efficient systems to report and address water cleanliness problems. Community Water Watch solves this by providing a scalable, transparent, and community-driven solution to identify and manage water pollution through real-time reporting and AI-driven analysis.
Features

Image-Based Reporting: Users can upload images of water bodies, which are analyzed using a TensorFlow model to detect cleanliness levels.
Blockchain Integration: Verified reports are stored on a blockchain using Web3, ensuring transparency and immutability.
User Dashboard: Built with React, the dashboard displays user profiles, report statuses, and a Leaflet map for visualizing water issue locations.
Cleanliness-Themed UI: The interface uses soft blues and greens to reflect the project's focus on clean water.
OTP Authentication: Secure user registration and login via Twilio OTP for phone-based authentication.
Database Management: MongoDB stores user data and reports (excluding "Clean" classifications, as per your requirement).
API Endpoints: Flask-powered backend with endpoints like /predict for image analysis and /user/send_otp for authentication.

Technologies Used

Frontend: React, React-Leaflet, Tailwind CSS, Framer Motion
Backend: Flask, Python
AI/ML: TensorFlow, OpenCV
Database: MongoDB
Blockchain: Web3
Authentication: Twilio for OTP
Deployment: Local development (extendable to cloud platforms like GCP)

Installation
Prerequisites

Python 3.8+
Node.js 16+
MongoDB
Git
A Web3-compatible blockchain node (e.g., Ethereum testnet)
Twilio account for OTP functionality

Setup Instructions

Clone the Repository:
git clone https://github.com/your-username/community-water-watch.git
cd community-water-watch


Backend Setup:

Install Python dependencies:pip install -r requirements.txt


Configure environment variables in a .env file:FLASK_APP=app.py
SECRET_KEY=your_secret_key
MONGODB_URI=your_mongodb_uri
TWILIO_ACCOUNT_SID=your_twilio_sid
TWILIO_AUTH_TOKEN=your_twilio_token
WEB3_PROVIDER=your_web3_provider_url


Run the Flask server:flask run




Frontend Setup:

Navigate to the frontend directory:cd frontend


Install Node.js dependencies:npm install


Start the React development server:npm start




MongoDB Setup:

Ensure MongoDB is running locally or provide a cloud MongoDB URI.
Initialize the database with the provided schema in db_schema.py.


Blockchain Setup:

Connect to a Web3 provider (e.g., Infura, Alchemy).
Deploy the smart contract using the provided contracts/ directory.


Testing:

Run backend tests:python -m unittest discover tests


Test image uploads and predictions using the /predict endpoint.



Usage

User Registration:

Register via the /user/send_otp endpoint using a phone number.
Verify the OTP to log in.


Reporting Water Issues:

Upload an image of a water body through the React frontend.
The TensorFlow model classifies the image as "Clean" or "Littered."
"Littered" reports are saved to MongoDB and logged on the blockchain.


Viewing Reports:

Access the dashboard to view your reports and their statuses.
Use the interactive Leaflet map to see reported locations.



Project Structure
community-water-watch/
├── backend/
│   ├── app.py              # Flask application
│   ├── models/            # TensorFlow model for image classification
│   ├── contracts/         # Blockchain smart contracts
│   ├── tests/             # Unit tests
│   └── requirements.txt    # Python dependencies
├── frontend/
│   ├── src/
│   │   ├── components/    # React components (e.g., UploadPage.jsx)
│   │   ├── pages/         # Dashboard, map, and report pages
│   │   └── assets/        # Images and styles
│   ├── package.json       # Node.js dependencies
│   └── tailwind.config.js # Tailwind CSS configuration
├── README.md              # This file
└── .env                   # Environment variables

Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature).
Commit your changes (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a Pull Request.

Please ensure your code follows the project's coding standards and includes tests.


Inspired by global water quality initiatives like GEO AquaWatch.
Built with open-source tools and libraries.
Special thanks to the community for feedback and support.

