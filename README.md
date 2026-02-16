# 🎓 Validity Authenticator for Academia

A **web-based application** designed to verify the authenticity of academic documents (such as student certificates) using **Optical Character Recognition (OCR)**.  

The system allows users to upload document images, extracts text content via Python, and cross-references the extracted data with a secure SQL database to validate student records.

---

## 🚀 Features

- 📤 **Document Upload**  
  Web interface for uploading certificate images (PNG, JPEG, etc.)

- 🔍 **Automated OCR Processing**  
  Extracts text from images using a Python OCR script integrated with the Node.js backend.

- ✅ **Validation Logic**  
  Verifies extracted details (e.g., Roll Number, Certificate ID) against a MySQL database.

- 💻 **Responsive Frontend**  
  Simple and user-friendly web interface built using HTML, CSS, and JavaScript.

---

## 🛠️ Tech Stack

### 🔹 Frontend
- HTML5  
- CSS3  
- JavaScript  

### 🔹 Backend
- Node.js  
- Express.js  

### 🔹 Database
- MySQL  

### 🔹 OCR Engine
- Python (utilized via child processes)

### 🔹 Dependencies
- express  
- multer  
- mysql2  
- cors  

---

## 📂 Project Structure

```plaintext
validity-authenticator-for-academia/
├── server/                 # Backend logic
│   ├── app.js              # Entry point for the Node.js application
│   ├── routes/             
│   │   └── upload.js       # Handles file upload & verification logic
│   ├── services/           
│   │   ├── db.js           # Database connection configuration
│   │   └── ocrRunner.js    # Interface for running Python OCR scripts
│   └── uploads/            # Temporary storage for uploaded files
├── web/                    # Frontend user interface
│   ├── index.html          # Main landing page
│   ├── Login.html          # Admin/User login page
│   ├── style.css           # Styling
│   └── script.js           # Frontend logic & API calls
├── python/                 # OCR Logic
│   └── ocr_extract.py      # Script to extract text from images
└── sql/                    
    └── schema.sql          # SQL scripts for creating tables
```

---

## ⚙️ Installation & Setup

### 📌 Prerequisites

- Node.js installed  
- Python installed (with required OCR libraries)  
- MySQL installed and running  

---

### 1️⃣ Database Setup

Run the `schema.sql` file in your MySQL instance:

```bash
mysql -u root -p < sql/schema.sql
```

---

### 2️⃣ Backend Setup

Navigate to the `server` directory and install dependencies:

```bash
cd server
npm install
```

Ensure your database credentials are correctly configured in:

```
server/services/db.js
```

Start the server:

```bash
npm start
# OR
node app.js
```

---

### 3️⃣ Python Requirements

Install required Python packages:

```bash
pip install pytesseract Pillow
```

⚠️ Make sure Tesseract OCR is installed on your system and added to your system PATH.

---

### 4️⃣ Running the Application

Once the backend server is running (usually on port **3000** or **8080**):

1. Open `web/index.html` in your browser.
2. Upload a certificate image.
3. Click **Submit/Verify**.
4. The system will display whether the document is **Valid** or **Invalid** based on database records.

---

## 📝 Usage Flow

1. User uploads certificate image  
2. Backend stores file temporarily  
3. Python OCR extracts text  
4. Extracted data is validated against MySQL database  
5. Result is returned to frontend  

---

## 🔐 Purpose

This project demonstrates:

- Integration between **Node.js and Python**
- Backend database validation logic
- OCR implementation in real-world use case
- Full-stack web application development

### ⭐ If you find this project useful, consider starring the repository.
