# AI101 xAPI Course

## 🏗 Project Overview
This project is an interactive **AI101 course** designed using **HTML and JavaScript**, integrated with **xAPI (Experience API)** to track learner interactions. The course consists of multiple lessons, each with structured content, interactive quizzes, and xAPI tracking to record user engagement and learning progress.

Key Features:
- 📚 Structured lessons on **Artificial Intelligence** and **Machine Learning**.
- 🎯 **xAPI integration** for tracking learner interactions (e.g., lesson views, quiz attempts, video plays).
- 📝 **MCQ and open-ended quizzes** to test learner understanding.
- 📊 Data tracking and reporting via an **xAPI Learning Record Store (LRS)**.
- 🌍 Web-based format, deployable on any web server or LMS supporting xAPI.

---

## 🔧 How to Set Up and Run It
### **1️⃣ Clone or Download the Repository**
```sh
# Clone the repository
git clone https://github.com/yourusername/AI101-xAPI-Course.git
cd AI101-xAPI-Course
```
Or download the ZIP file and extract it.

### **2️⃣ Open in a Web Browser**
Simply open `ai101.html` in your preferred browser:
- **Windows/Mac/Linux**: Double-click `ai101.html` or open it manually in **Chrome, Firefox, or Edge**.

### **3️⃣ Configure xAPI Endpoint (Optional)**
If using a custom xAPI Learning Record Store (LRS), update the `xAPIWrapper` configuration in `xapiwrapper.min.js`.
```js
var conf = {
    "endpoint": "https://your-lrs-endpoint/xAPI/",
    "auth": "Basic " + btoa("username:password")
};
ADL.XAPIWrapper.changeConfig(conf);
```

### **4️⃣ Run Locally with a Simple HTTP Server** (For API Requests)
If the xAPI requests are blocked due to CORS, serve the files using Python or Node.js:
```sh
# Python (3.x)
python -m http.server 8000
# Node.js
npx http-server -p 8000
```
Then access: `http://localhost:8000/ai101.html`

---

## 🎯 xAPI Tracking and Implementation
This course tracks the following interactions using xAPI:
- **Course Viewed** (`viewed`)
- **Lesson Interacted** (`interacted`)
- **Lesson Started** (`experienced`)
- **Lesson Completed** (`completed`)
- **Quiz Attempted** (`answered`)
- **Video Watched** (`experienced`)

Example xAPI Statement Sent:
```json
{
    "actor": {
        "name": "Jane Doe",
        "mbox": "mailto:jane.doe@vorwerk.de"
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/viewed",
        "display": {"en-US": "viewed"}
    },
    "object": {
        "id": "http://vorwerk.de/xapi/lesson1",
        "definition": {
            "name": {"en-US": "Lesson 1: What is AI?"},
            "description": {"en-US": "User interacted with Lesson 1"}
        }
    }
}
```

---

## 📂 Folder Structure
```
AI101-xAPI-Course/
│── ai101.html             # Course Overview Page / or landing page 
│── lesson1.html           # Lesson 1 Content
│── lesson1_quiz.html      # Lesson 1 Quiz
│── lesson2.html           # Lesson 2 Content
│── lesson2_quiz.html      # Lesson 2 Quiz
│── lesson3.html           # Lesson 3 Content
│── lesson3_quiz.html      # Lesson 3 Quiz
│── assets/                # Images, CSS, and other assets
│── scripts/
│   ├── xapiwrapper.min.js # xAPI Library
│   ├── cryptojs_v3.1.2.js # Cryptographic Functions
│── README.md              # Project Documentation
```

---

## 💡 How to Contribute or Extend It
### **1️⃣ Add New Lessons**
- Create a new lesson file (`lesson4.html`).
- Follow the same structure as `lesson1.html`.
- Update `ai101.html` to include the new lesson link.

### **2️⃣ Customize xAPI Tracking**
- Modify `xapiwrapper.min.js` to track additional user interactions.

### **3️⃣ Style Improvements**
- Edit `styles.css` to improve UI/UX.

### **4️⃣ Enhance AI Tutor Feedback**
- Extend AI tutor logic to provide dynamic feedback based on user responses.

---

## 👨‍💻 Who to Contact for Support
If you have any questions or issues, please reach out to:
- **Project Owner:** Zoey Azimi (@zoeyazimi)
- **Company:** Vorwerk
- **GitHub Issues:** Submit a bug report or feature request [here](https://github.com/yourusername/AI101-xAPI-Course/issues)

---

### 🚀 Happy Learning! 🎓

