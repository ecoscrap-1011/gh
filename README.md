# AI-Powered Phishing Website Detection

## Cover Page

**AI-Powered Phishing Website Detection**
**Submitted in partial fulfillment of the requirements**
for the degree of **Bachelor of Technology**
Department of Computer Science and Engineering
\[Your College Name]
\[Year]

---

## Certificate

This is to certify that the project entitled **"AI-Powered Phishing Website Detection"** submitted by **\[Your Name]** (Roll No: \[XXXXXX]) in partial fulfillment of the requirements for the award of the degree of **Bachelor of Technology** in **Computer Science and Engineering**, is a record of bona fide work carried out by them under our supervision.

**Supervisor Name**
Designation
Department of CSE

---

## Acknowledgement

I would like to express my sincere gratitude to my guide **\[Supervisor Name]**, for their invaluable support and guidance throughout this project. Their expertise and insights helped me overcome various challenges and enriched my learning experience.

I also extend my gratitude to the faculty members and staff of the Department of Computer Science and Engineering for their continuous encouragement and assistance. I am deeply thankful to my family and friends for their patience, understanding, and constant support throughout this journey.

---

## Abstract

With the rise of digital communication and online transactions, phishing attacks have become increasingly sophisticated and widespread. These attacks involve the use of deceptive websites designed to mimic legitimate platforms in order to trick users into revealing sensitive information such as login credentials, financial data, or personal details.

This project presents an AI-powered approach to phishing website detection that leverages a combination of behavioral prediction models, threat intelligence services, and real-time API integration. The proposed system integrates Prophet-based behavioral time series prediction with data from VirusTotal and CAN API to deliver accurate threat assessments.

Developed using a full-stack Next.js framework, the system offers a clean and intuitive user interface styled with Tailwind CSS and enhanced with dynamic visualizations such as charts and graphs. It allows users to input URLs, upload suspicious files, and query IP addresses, offering a comprehensive solution for identifying and mitigating phishing threats in real time.

The application can serve as a valuable tool for individuals, organizations, and cybersecurity professionals aiming to enhance online security and defend against phishing attacks.

---

## Table of Contents

1. Introduction
2. Requirement Analysis
3. System Design
4. Implementation
5. Testing
6. Results and Discussion
7. Conclusion and Future Work
8. Appendices

   * Source Code
   * Project Schedule
   * Bibliography

---

## Chapter 1: Introduction

### 1.1 Background

Phishing websites are malicious digital platforms designed to deceive users by masquerading as trustworthy entities. These sites often closely resemble legitimate login pages, banking portals, or service platforms. Once a user inputs their data, the information is harvested by attackers for fraudulent activities.

The origins of phishing can be traced back to the mid-1990s, evolving from basic email scams to complex, highly targeted campaigns known as spear phishing. As internet usage has surged, phishing attacks have become one of the most common cyber threats, causing billions of dollars in damages globally.

Traditional detection techniques rely on blacklists and static rule-based systems, which are often insufficient due to their inability to detect zero-day threats or previously unknown phishing domains. There is a need for adaptive, intelligent systems that can detect novel phishing strategies and provide real-time insights.

### 1.2 Problem Statement

The major challenge addressed in this project is the lack of an intelligent, real-time phishing detection mechanism that can process various types of input data (URLs, files, IP addresses) and classify them as either legitimate or malicious based on dynamic threat intelligence and AI-driven prediction.

The solution aims to bridge the gap between static security models and dynamic threat environments by incorporating machine learning and external threat databases into a unified detection framework.

### 1.3 Objectives

* To build a comprehensive web platform capable of analyzing URLs, files, and IP addresses.
* To utilize VirusTotal and CAN APIs for real-time threat intelligence.
* To apply the Prophet forecasting model to identify anomalous behavior patterns indicative of phishing.
* To design a responsive and user-friendly UI using Tailwind CSS.
* To visualize results using interactive charts and intuitive dashboards.
* To implement secure, scalable, and modular backend API routes.

### 1.4 Methodology

The proposed system follows a layered architecture, beginning from user interaction to threat analysis and result presentation:

1. **User Input Layer:** Users input data through forms—URLs, files, or IPs.
2. **Data Fetch Layer:** Backend APIs communicate with VirusTotal and CAN API to retrieve threat intelligence.
3. **Prediction Layer:** Prophet model processes the input to detect patterns or anomalies.
4. **Visualization Layer:** Results are displayed via charts, cards, and alerts using Tailwind and JavaScript-based libraries.

Each component of the system is designed to work independently and asynchronously, ensuring optimal performance even under high user loads.

### 1.5 Scope of the Project

This project focuses on detecting phishing attempts through analysis of websites (URLs), uploaded documents (PDFs, executables), and IP address activity. It supports real-time and retrospective analysis using both API-driven data and ML models.

The system does not currently handle phishing detection in emails or social media platforms, although the architecture can be extended to include these features in future iterations.

The project is scalable and can be transformed into a browser plugin, mobile app, or integrated into enterprise cybersecurity workflows.

### 1.6 Significance of the Study

Phishing is one of the most prevalent and damaging forms of cyberattack. By offering a proactive, AI-driven approach to detection, this system empowers users to defend themselves against online threats.

Unlike static blacklists, the AI component continuously learns and adapts to new attack patterns, offering a dynamic line of defense. Moreover, the integration of reputable external APIs adds credibility and depth to the detection process.

This study is valuable for cybersecurity researchers, IT professionals, and software developers aiming to incorporate intelligent threat detection into their products or services.


---

## Chapter 2: Requirement Analysis

### 2.1 Functional Requirements

* URL Input and Scan
* File Upload and Scan
* IP Address Lookup
* Fetch data from VirusTotal and CAN API
* Generate visual summaries
* Predict phishing likelihood using Prophet

### 2.2 Non-Functional Requirements

* Fast and responsive UI
* Secure API communication
* Error handling and logging

### 2.3 System Requirements

**Software:**

* Node.js, Next.js
* Prophet (Python)
* Tailwind CSS

**Hardware:**

* 4 GB RAM minimum
* Modern browser

### 2.4 Requirement Gathering

* Stakeholder interviews
* Research on phishing techniques
* Review of VirusTotal and CAN APIs

### 2.5 Classification

* User Requirements
* System Functional Requirements
* System Interface Requirements

---

## Chapter 3: System Design

### 3.1 Use Case Diagram

* **Actor:** User
* **Use Cases:** Scan URL, Scan File, Lookup IP, View Results, Analyze Report

### 3.2 Sequence Diagram

* **Steps:** User submits data (URL/IP/File) → Backend fetches data → Prophet processes → UI shows results

### 3.3 DFD (Level 0, 1)

* **Level 0:** Input (URL/IP/File) → Analysis → Output Result
* **Level 1:** VirusTotal → CAN API → Prophet → Report

### 3.4 Schema Design

Tables: `scans`, `results`, `ip_logs`, `file_logs`, `api_logs`

### 3.5 Package Diagram

* Frontend: `file-scanner/page.jsx`, `ip-lookup/page.jsx`, `UrlScanner/page.jsx`
* Backend API: `/api/url-scan/route.js`, `/api/file-scan/route.js`, `/api/ip-data/route.js`, etc.
* Supporting files: `layout.js`, `globals.css`, `page.jsx`

---

## Chapter 4: Implementation

### 4.1 Technology Stack

* **Frontend:** Next.js, Tailwind CSS
* **Backend:** Next.js API routes, Python Prophet Model
* **APIs:** VirusTotal, CAN API

### 4.2 Folder Structure (Simplified)

```
C:.
├───api
│   ├───file-scan
│   ├───ip-data
│   ├───ip-details
│   ├───recent-scans
│   ├───scan-stats
│   ├───url-scan
│   └───VT-scan-url
├───file-scanner
├───ip-lookup
└───UrlScanner
```

### 4.3 API Routes

* `/api/url-scan/route.js`
* `/api/file-scan/route.js`
* `/api/ip-data/route.js`
* `/api/ip-details/route.js`
* `/api/scan-stats/route.js`
* `/api/recent-scans/route.js`
* `/api/VT-scan-url/route.js`

### 4.4 Frontend Components

* FileScanner, IpLookup, UrlScanner
* ScanForm, ScanResultChart, ResultPanel, Toasts, Tables, Cards

### 4.5 Screenshots

* \[Placeholder for UI screenshots with captions]

---

## Chapter 5: Testing

### 5.1 Test Cases

| Test | Input                                | Expected Output | Actual Output | Status |
| ---- | ------------------------------------ | --------------- | ------------- | ------ |
| 1    | [http://phish.com](http://phish.com) | Phishing        | Phishing      | Pass   |
| 2    | 8.8.8.8                              | Safe IP         | Safe IP       | Pass   |
| 3    | Malicious PDF                        | Detected Threat | Detected      | Pass   |

### 5.2 Test Tools

* Postman
* Console logs
* Browser testing

### 5.3 Results

* All major paths tested
* Errors caught via API error handlers
* Model integrated and validated with sample inputs

---

## Chapter 6: Results and Discussion

* Successfully scanned URLs, IPs, and files
* Charts and tables helped user interpretation
* Prophet model provided classification with time-aware prediction
* VirusTotal and CAN API enhanced detection quality
* Rate limits managed with fallback alerts

---

## Chapter 7: Conclusion and Future Work

* AI + API integration helps detect phishing accurately
* Full-stack system offers complete threat scanning workflow
* Can be extended to browser extensions, email links
* Add offline caching, user login, multi-language UI support in future

---

## Appendices

### Appendix A: Source Code

* Custom routes and UI files only (exclude auto-generated)

### Appendix B: Project Schedule

| Week | Activity                      |
| ---- | ----------------------------- |
| 1    | Requirements Gathering        |
| 2    | API Integration               |
| 3    | Frontend Implementation       |
| 4    | Model Integration             |
| 5    | Testing and Debugging         |
| 6    | Documentation and Report Prep |

### Appendix C: Bibliography

* VirusTotal API Docs
* CAN API Docs
* Prophet Forecasting Docs
* OWASP Guidelines
* Tailwind CSS Docs
* Next.js Docs

### Acronyms

| Acronym | Full Form                         |
| ------- | --------------------------------- |
| AI      | Artificial Intelligence           |
| API     | Application Programming Interface |
| CSS     | Cascading Style Sheets            |
| IP      | Internet Protocol                 |
| UI      | User Interface                    |
| URL     | Uniform Resource Locator          |
| VT      | VirusTotal                        |
