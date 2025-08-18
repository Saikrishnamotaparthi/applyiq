# ApplyIQ: AI-Powered Resume Analyzer 🚀

[![Deployment](https://img.shields.io/badge/Live%20Demo-ApplyIQ.saikrishnamotaparthi.tech-brightgreen?style=for-the-badge&logo=vercel)](https://applyiq.saikrishnamotaparthi.tech)
[![Technology](https://img.shields.io/badge/Tech%20Stack-n8n%20%7C%20Gemini%20AI%20%7C%20JS-blueviolet?style=for-the-badge)](https://n8n.io/)

**ApplyIQ** is a modern, AI-driven web application that instantly analyzes your resume against a job description, giving you the critical feedback needed to land your next interview.

Built with a powerful **n8n** automation workflow and **Google's Gemini AI**, this tool provides a clear "Fit Score," a breakdown of your resume's pros and cons, and a list of missing keywords. The goal is to empower job seekers to tailor their applications with precision and confidence.

---

### ✨ Features

* **Intelligent AI Analysis:** Leverages the power of Google Gemini to understand the context and nuances of both your resume and the job description.  
* **Dynamic "Fit Score" Gauge:** An animated, futuristic meter provides an immediate score (0-100) on how well your resume matches the role.  
* **Actionable Feedback:** The analysis is broken down into three easy-to-understand sections:  
  * ✅ **Pros (Strengths):** What the AI identified as key strengths and aligned experiences.  
  * ❌ **Cons (Gaps):** Clear pointers on where your resume falls short.  
  * 🔑 **Missing Keywords:** A list of critical terms from the job description that should be included in your resume.  
* **Clear Verdict:** A concise, AI-generated summary and a clear "Ideal Match" or "Not an Ideal Match" verdict.  
* **Stunning, Responsive UI:**  
  * Full-screen animated video backgrounds (desktop and mobile versions).  
  * A sleek, modern "glassmorphism" and aurora UI design.  
  * Interactive drag-and-drop zones for a seamless user experience.  

---

### 🎥 Live Demo & Screenshots

**Try the live application here:**  
### [https://applyiq.saikrishnamotaparthi.tech](https://applyiq.saikrishnamotaparthi.tech)

*(**Tip:** To get these URLs, simply take screenshots, drag them into a new GitHub Issue in your repository, and copy the image URLs that are generated.)*

---

### 🛠️ Technology Stack & Architecture

This project demonstrates a powerful, modern approach to building a "serverless" application using a visual automation platform as the backend.

#### **Front-End:**
* **HTML5, CSS3, & Vanilla JavaScript (ES6+):** No frameworks were used, ensuring a fast, lightweight, and dependency-free user experience.  
* **Hosting:** Deployed as a static site using **GitHub Pages**.  

#### **Back-End:**
* **n8n (Local Instance):** The entire backend logic is contained within a single n8n workflow running on a local machine.  
* **Google Gemini Pro:** The AI model used for the core analysis, accessed via its API.  

#### **How it Works:**
1. **Upload:** The user uploads a resume PDF and a job description PDF on the `index.html` page.  
2. **Request:** The browser sends the files via `FormData` directly to a dedicated n8n Webhook URL.  
3. **Process:** The n8n workflow is triggered and executes the following steps:  
   * Receives the files.  
   * Uses **Extract From PDF** nodes to read the text content.  
   * An **Edit Fields** node cleans and structures the text.  
   * A **Google Gemini** node sends a detailed prompt with the text to the AI.  
   * A **Code** node parses the AI's JSON response and shapes it into the final output format.  
4. **Respond:** An n8n **Respond to Webhook** node sends the final, structured JSON data back to the browser.  
5. **Render:** The browser's JavaScript receives the JSON and dynamically builds the beautiful results UI.  
