# 📚 AI Course with xAPI Tracking

## 🏗 Project Overview
This project is an **HTML-based interactive AI course** with **xAPI tracking** for learning analytics. It tracks user interactions, such as:
- Viewing the course
- Interacting with lessons
- Completing quizzes
- Watching videos
- Submitting open-ended responses

The xAPI statements are sent to the **ADL Learning Record Store (LRS)**, allowing for detailed learner analytics.

## 🔧 How to Set Up and Run It
### 1️⃣ Clone the Repository
```sh
git clone https://github.com/zoeyazimi/ai-xapi-course.git
cd ai-xapi-course
```

### 2️⃣ Open the Course Locally
Simply open `index.html` (or `ai101.html`) in a web browser to access the course.

### 3️⃣ Configure xAPI Credentials (Optional)
If you want to track learner data using **xAPI**, update `xapiwrapper.min.js` or `ai101.html` with your own **LRS credentials**:
```js
var conf = {
    "endpoint": "https://lrs.adlnet.gov/xAPI/",
    "auth": "auth": "Basic " + btoa("username:password") #YOUR_BASE64_ENCODED_CREDENTIALS
};
ADL.XAPIWrapper.changeConfig(conf);
```
**Note1:** You can create your own **free ADL LRS account** at **[ADL LRS](https://lrs.adlnet.gov/)**.
**Note2:**The interaction will be visible in your account and undr **my statements**  

## 🎯 xAPI Tracking and Implementation
This course uses **xAPI statements** to track user interactions. Here’s how they are sent:

- **Viewed Course:** `sendStatement('viewed', 'ai101', 'Introduction to AI Course');`
- **Interacted with a Lesson:** `sendStatement('interacted', 'lesson1', 'Lesson 1: What is AI?');`
- **Completed a Quiz:** `sendStatement('answered', 'lesson1-quiz', 'Lesson 1 Quiz');`
- **Watched Video:** `sendStatement('experienced', 'lesson1-video', 'AI Evolution Video');`

Each statement includes the **actor (learner), verb, and object** to store learner activity in the LRS.

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
│── scr/
│   ├── xapiwrapper.min.js # xAPI Library
│   ├── cryptojs_v3.1.2.js # Cryptographic Functions
│── README.md              # Project Documentation
```

## 💡 How to Contribute or Extend It
### 🛠️ Adding New Lessons
1. Create `lessonX.html` for the new lesson.
2. Create `lessonX_quiz.html` for the quiz.
3. Update `ai101.html` to include a button for the new lesson or content.
4. Implement xAPI tracking for the new lesson.

### 🎨 Customizing the UI
- Modify `assets/styles.css` to change the look and feel.
- Add new videos or interactive content to enhance learning.

### 🔗 Connecting to Another LRS
- Replace `https://lrs.adlnet.gov/xAPI/` with another LRS endpoint in `xapiwrapper.min.js`.

## 👨‍💻 Who to Contact for Support
For any issues or questions, feel free to reach out to:
- **Zoey Azimi** - zoey.azimi@company.com
- **GitHub Issues** - Submit a bug report or feature request [here](https://github.com/yourusername/AI101-xAPI-Course/issues)

---
### 🚀 Ready to track learning analytics? Clone the repo, set up xAPI, and start tracking interactions! 🎯
