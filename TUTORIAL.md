# 📘 AI-900 Exam Dashboard — Complete Tutorial

> A step-by-step guide for adding exams, taking quizzes, and customizing your practice dashboard.

---

## 📋 Table of Contents
1. [What Is This?](#1-what-is-this)
2. [Quick Start](#2-quick-start)
3. [How It Works](#3-how-it-works)
4. [Adding Exams (Upload Files)](#4-adding-exams-upload-files)
5. [Question File Format Guide](#5-question-file-format-guide)
6. [Taking an Exam](#6-taking-an-exam)
7. [Managing Your Exams](#7-managing-your-exams)
8. [Features Explained](#8-features-explained)
9. [Dark/Light Theme](#9-darklight-theme)
10. [Progress Tracking](#10-progress-tracking)
11. [Troubleshooting](#11-troubleshooting)

---

## 1. What Is This?

This is a **web-based exam practice dashboard** that runs entirely in your browser. You don't need a server, database, or internet connection (after initial load). It reads your exam questions from simple text files (`.md` or `.txt`) and presents them as interactive quizzes.

**Key features:**
- ✅ Upload or drag-and-drop exam files
- ✅ Interactive quiz with 4-option multiple choice
- ✅ Instant feedback (correct/wrong with explanations)
- ✅ Progress tracking across sessions
- ✅ Domain-wise score breakdown
- ✅ Practice wrong answers only
- ✅ Dark and light themes
- ✅ Works offline after first load
- ✅ All data saved in your browser (localStorage)

---

## 2. Quick Start

### Option A: Use the Live Website
Simply visit: **https://natarajvd.github.io/ai-900-exam-dashboard/**

The site comes with a bundled 60-question practice exam pre-loaded.

### Option B: Run Locally
1. Download this repository (green "Code" → "Download ZIP")
2. Extract the folder
3. Double-click **`exam-hub.html`** to open in your browser
4. Done! Start taking the practice exam or upload your own.

---

## 3. How It Works

```
┌─────────────────────────────────────────┐
│           exam-hub.html                  │
│  (Dashboard UI + JavaScript Logic)       │
│                                          │
│  ┌──────────┐    ┌──────────────────┐   │
│  │ Library  │───▶│ Exam Screen      │   │
│  │ Screen   │    │ (Questions)      │   │
│  │          │    │                  │   │
│  │ • List   │    │ • Q1, Q2, Q3...  │   │
│  │ • Add    │    │ • Instant answer │   │
│  │ • Delete │    │ • Score card     │   │
│  └──────────┘    └──────────────────┘   │
│                                          │
│  ┌──────────────────────────────────┐   │
│  │  localStorage (Browser Storage)  │   │
│  │  • Exams list                    │   │
│  │  • Answers                       │   │
│  │  • Progress                      │   │
│  └──────────────────────────────────┘   │
└─────────────────────────────────────────┘
```

Everything runs in your browser. Your exams, answers, and progress are stored in **localStorage** — no data is sent anywhere.

---

## 4. Adding Exams (Upload Files)

### Method 1: Drag & Drop (Easiest)
1. Open the dashboard
2. Find the **"Drag & Drop"** zone at the top
3. Drag your `.md` or `.txt` question file onto it
4. The exam appears instantly in your library

### Method 2: Click to Upload
1. Click the **"+ Add Exam"** button
2. Select `.md` or `.txt` files from your computer
3. Exams are added to your library

### Method 3: Pre-bundled (For Self-Hosting)
If you're running locally, place your question files in the same folder and upload them. The files stay on your machine — nothing is uploaded to any server.

---

## 5. Question File Format Guide

Your exam file must follow this format. The dashboard parses it automatically.

### Basic Structure

```markdown
# Exam Title: Your Exam Name Here

## Module: Module Name

### Q1
Your question text goes here?

- **A.** First option
- **B.** Second option
- **C.** Third option
- **D.** Fourth option

**Correct answer:** B

**Explanation:** Your explanation for why B is correct.

### Q2
Second question?

- **A.** Option 1
- **B.** Option 2
- **C.** Option 3
- **D.** Option 4

**Correct answer:** A
**Explanation:** Explanation here.
```

### Supported Format Variations

The parser is smart and handles these variations:

| What You Write | How It's Parsed |
|---|---|
| `### Q1` or `### Question 1` | Question number detected |
| `- **A.** text` or `A) text` or `a) text` | Option A |
| `**Correct answer:** B` or `**Answer:** B` or `**Answer: B**` | Correct option |
| `**Explanation:** text` or `**Explanation:**text` | Explanation text |

### Multi-Domain Support

You can have questions from different topics/domains:

```markdown
# AI-900 Practice Exam

## AI Fundamentals

### Q1
What is AI?
- **A.** Artificial Intelligence
- **B.** ...
- **C.** ...
- **D.** ...
**Correct answer:** A
**Explanation:** ...

## Machine Learning

### Q1
What is ML?
- **A.** Machine Learning
- **B.** ...
- **C.** ...
- **D.** ...
**Correct answer:** A
**Explanation:** ...
```

The exam will show questions in randomized order, but your results will group scores by domain.

### Quick Checklist for Creating Exam Files
- ✅ Start with `# Exam Title:` to set the exam name
- ✅ Use `## Module:` to define question domains (optional)
- ✅ Use `### Q1`, `### Q2`, etc. for each question
- ✅ Each question needs 4 options (A, B, C, D)
- ✅ Each question needs a correct answer line
- ✅ Explanation is optional but recommended
- ✅ Save as `.md` (Markdown) or `.txt` file
- ❌ Don't leave any question without 4 options
- ❌ Don't use HTML tags in questions (may break parsing)

### Pro Tips
- The **exam title** is shown on the dashboard card
- The **exam count** (number of questions) determines your score
- You can **add multiple exams** — they show as separate cards
- Exam files are **only read once** — after upload, the data lives in your browser

---

## 6. Taking an Exam

1. **Go to the Library** — You'll see cards for each exam
2. **Click "Start Exam"** on any exam card
3. **Answer questions** — Click any option to select it
4. **Instant feedback** — Green (correct) or Red (wrong) with explanation
5. **Navigate** — Use ← → arrows or the Progress Dots at the top
6. **Flag questions** — Click the ⚑ flag icon to mark for later review
7. **Finish** — Click "Finish Exam" when done
8. **Score Card** — See your results with domain breakdown

### During the Exam
- **Show correct answer** is always visible (green text at bottom)
- **Explanation** appears when you select an answer
- **Time started** is shown at the top
- **Your progress** (e.g., "3/60 answered") updates live
- **Score updates** live (e.g., "52% (5/10 answered)")

### After Finishing
- **Score Card** shows: Total questions, Attempted, Correct, Wrong, Unattempted, Score %
- **Domain Breakdown** shows your score per topic
- **"Practice Again"** — Reset and retake
- **"Practice Wrong Only"** — Focus on questions you got wrong
- **"View All"** — Review the full exam

---

## 7. Managing Your Exams

### Deleting an Exam
1. Hover over an exam card in the library
2. Click the **🗑️ (trash)** icon on the card
3. Confirm the deletion

⚠️ This is permanent. Once deleted, the exam is removed from your browser.

### Adding More Exams
Just upload another file! You can have unlimited exams in your library.

### Exam Order
Exams are sorted automatically: **Unattempted → In Progress → Completed**

### Pre-bundled Exam
The dashboard ships with a **60-question AI-900 practice exam** built-in. This loads automatically for first-time visitors. You cannot delete it (it reloads if removed), but you can clear your browser data to reset.

---

## 8. Features Explained

### Progress Dots
The row of small dots at the top of the exam screen shows:
- ⬜ **Empty** = Not yet answered
- 🟩 **Green** = Answered correctly
- 🟥 **Red** = Answered incorrectly
- ⚑ **Flagged** = Marked for review

### Domain Breakdown
After finishing an exam, your results show performance per topic:
```
| AI Fundamentals | 8/10 correct | 80% |
| Machine Learning | 6/8 correct | 75% |
```

### Wrong Answer Practice
The "Practice Wrong Only" mode lets you:
- Retake only the questions you got wrong
- Focus on your weak areas
- Exit anytime to return to the full exam

### Autosave (Session Resume)
If you close the browser mid-exam, your progress is saved. When you return:
- Your answers are remembered
- Your flagged questions are remembered
- You see "Resume Exam?" with "Resume" and "Reset" buttons

---

## 9. Dark/Light Theme

Click the **🌙 / ☀️** button (top-right corner) to toggle between dark and light mode. Your preference is saved automatically.

---

## 10. Progress Tracking

All your exam progress is stored in your browser's **localStorage**. This means:
- ✅ Your data persists across browser sessions
- ✅ No login or account needed
- ❌ Clearing browser data resets everything
- ❌ Progress doesn't sync across devices/browsers

To back up your progress: Your browser data is local-only. There's no export feature currently.

---

## 11. Troubleshooting

### "Exam won't load / Nothing shows up"
- ✅ Make sure your file uses the correct format (see Section 5)
- ✅ Check file extension is `.md` or `.txt`
- ✅ The file must have at least 1 properly formatted question

### "Questions don't appear after uploading"
- Check the console for errors (F12 → Console)
- Make sure each question has 4 options (A, B, C, D)
- The "Correct answer" line must match one of the options

### "My progress is gone"
- Did you clear browser data? That removes localStorage
- Try a different browser — data doesn't sync across browsers

### "The page looks broken"
- Open the page in a modern browser (Chrome, Edge, Firefox)
- Check internet connection (Tailwind CSS loads from CDN on first load)
- If running locally, make sure you opened `exam-hub.html` (not another .html file)

### "I want to share my exam file"
- Your `.md` or `.txt` question file can be shared with anyone
- They just need to upload it to their dashboard
- The file itself is independent of the dashboard

---

## 📁 File Structure

```
AI-900/
├── exam-hub.html          ← Main dashboard (open this!)
├── index.html             ← Auto-redirects to exam-hub.html
├── exam_format_guide.md   ← Question format reference
├── TUTORIAL.md            ← This file
├── README.md              ← Project overview
├── LICENSE                ← MIT License
├── .gitignore             ← Git ignore rules
└── tools/                 ← Python utilities (for developers)
```

---

*Built with ❤️ for Azure AI certification preparation.*
