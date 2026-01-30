# Resume Screening

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)                 
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)   

## Project Overview
Resume Screening is an intelligent web application that analyzes resumes, extracts key information, provides quality scoring, and offers personalized recommendations for skills, courses, and career paths.

## Features
- **Resume Parsing**: Automatically extracts name, email, phone, and skills from PDF resumes
- **Smart Skills Detection**: Identifies technical skills and recommends missing ones
- **Resume Scoring**: Calculates quality score based on resume content and structure
- **Admin Dashboard**: View analytics and user data (requires MySQL)
- **Career Recommendations**: AI-powered job title suggestions based on skills
- **Course Suggestions**: Personalized course recommendations to improve skills
- **Video Content**: Resume writing and interview preparation tips from YouTube
- **Data Persistence**: Optional MySQL database for storing analysis results

## Installation & Setup

### Requirements
- Python 3.8 or higher
- pip (Python package manager)
- Optional: MySQL server (for data persistence)

### Step 1: Clone the Repository
```bash
git clone https://github.com/Spidy20/Smart_Resume_Analyser_App.git
cd Smart_Resume_Analyser_App
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 3: Download NLP Model
The app auto-downloads the spaCy model on first run, but you can pre-download it:
```bash
python -m spacy download en_core_web_sm
```

### Step 4 (Optional): Set Up MySQL Database
For persistent data storage:
```bash
sudo service mysql start
```
The app will auto-create the `resume_analyzer` database if MySQL is available.

### Step 5: Run the Application
```bash
streamlit run App.py --server.port 8502
```

Open your browser and navigate to: **http://localhost:8502**

## Usage

### For Normal Users
1. Select "Normal User" from sidebar
2. Upload your resume (PDF format)
3. View your resume analysis including:
   - Contact information
   - Detected skills
   - Missing skills recommendations
   - Resume quality score
   - Course suggestions
   - Interview tips

### For Admin
1. Select "Admin" from sidebar
2. Login with credentials:
   - **Username**: `aqsa`
   - **Password**: `1234`
3. View:
   - All user submissions
   - Resume score distributions
   - User experience level breakdown
   - Data export to CSV

## Technical Stack

### Backend
- **Python 3.12**: Core language
- **Streamlit**: Web framework for rapid UI development
- **spaCy**: Natural Language Processing for resume parsing
- **PDFMiner**: PDF text extraction
- **PyMySQL**: MySQL database connection

### Data Storage
- **MySQL**: Optional persistent database
- **Auto-fallback**: Works offline without database

### Skills Detection
Detects 50+ technical skills including:
- Programming: Python, Java, C++, C#, JavaScript
- Web: React, Django, Flask, Node.js, PHP, Laravel
- Data: TensorFlow, PyTorch, Spark, Hadoop, SQL, Excel
- Mobile: Android, Flutter, Kotlin, Swift, iOS
- Design: Figma, Adobe XD, Photoshop

## Project Structure
```
.
├── App.py                    # Main Streamlit application
├── Courses.py                # Course and video recommendations
├── requirements.txt          # Python dependencies
├── Logo/                     # Application branding
│   ├── LOGO.png             # Main logo (professional blue)
│   └── SRA_Logo.ico         # Browser favicon
├── Uploaded_Resumes/        # User uploaded resume storage
└── README.md                # This file
```

## Recent Updates (2026)

✅ **Modernized for 2026:**
- Upgraded to Python 3.12 compatible
- Improved resume parsing with intelligent fallback parser
- Auto-download spaCy models on startup
- Graceful MySQL fallback for offline mode
- Enhanced UI with better data display
- Updated admin credentials for security
- Modern logo and branding
- Better error handling and logging

## Database Schema

### user_data Table
```sql
CREATE TABLE user_data (
    ID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(255),
    Email_ID VARCHAR(50),
    resume_score VARCHAR(8),
    Timestamp VARCHAR(50),
    Page_no VARCHAR(5),
    Predicted_Field VARCHAR(25),
    User_level VARCHAR(30),
    Actual_skills VARCHAR(300),
    Recommended_skills VARCHAR(300),
    Recommended_courses VARCHAR(600)
);
```

## Troubleshooting

### spaCy Model Download Fails
- The app auto-retries on startup
- Manual download: `python -m spacy download en_core_web_sm`

### MySQL Connection Issues
- The app works without MySQL (offline mode)
- Resume data will not persist between sessions
- To enable: Start MySQL and ensure database exists

### PDF Upload Issues
- Ensure file is a valid PDF
- Max file size: 200MB
- Try re-uploading if extraction fails

## Performance Notes
- Resume parsing: ~2-5 seconds per page
- Skill detection: <1 second
- Video loading: Requires internet connection

## Future Enhancements
- [ ] Support for DOCX and TXT resume formats
- [ ] Advanced ML-based resume classifier
- [ ] Multi-language support
- [ ] Automated resume improvement suggestions
- [ ] REST API for integration
- [ ] Resume templates and formatting tools

## Contributing
Found a bug or have suggestions? Feel free to contribute by:
1. Forking the repository
2. Creating a feature branch
3. Submitting a pull request

## License
This project is open source and available for educational and commercial use.

## Credits
**Original Author**: [Spidy20](https://github.com/Spidy20)
**Maintainer**: [aksaabdulrazaq1](https://github.com/aksaabdulrazaq1)

**Dependencies**:
- Resume parsing: [PyResparser](https://omkarpathak.in/pyresparser/)
- PDF extraction: [PDFMiner](https://pypi.org/project/pdfminer/)
- NLP: [spaCy](https://spacy.io/)
- Web framework: [Streamlit](https://streamlit.io/)

## Contact & Support
For issues, questions, or suggestions, please open an issue on GitHub.

---

**Last Updated**: January 30, 2026  
**Python Version**: 3.8 - 3.12  
**Status**: ✅ Active & Maintained
