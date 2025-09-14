
# Work Division: Prototype and Presentation

This document outlines the division of work for the prototype development and the final presentation, distributed among the 6 team members.

---

## Member 1: Project Lead & Backend Architect

- **Prototype Responsibilities:**
    - Lead the overall development process and ensure timely progress.
    - Design and build the core backend infrastructure (Node.js with Express.js).
    - Set up the database (MongoDB or PostgreSQL) and design the schema for hazard reports.
    - Create the primary API endpoints (`POST /api/reports`, `GET /api/reports`).

- **Presentation Responsibilities:**
    - **Slide 1: Idea Title & Detailed Explanation:** Take the lead on this slide. Explain the core concept, how it addresses the problem statement, and what makes the solution innovative.
    - **Overall Presentation:** Oversee the creation of the entire presentation to ensure a cohesive and compelling narrative.

---

## Member 2: Mobile App Developer (Web App Contributor)

- **Prototype Responsibilities:**
    - Collaborate with the Frontend Developer (Member 3) on building the **citizen-facing web application** for the prototype.
    - Implement the reporting form (hazard type, description, etc.).
    - Integrate the browser's geolocation API to automatically capture the user's location.
    - Connect the reporting form to the backend `POST /api/reports` endpoint.

- **Presentation Responsibilities:**
    - **Slide 2: Technical Approach:** Contribute to this slide by creating a flow chart or diagram that shows the user journey for submitting a report through the web app.
    - **Future Scope:** Briefly outline the plan for the native mobile app (iOS/Android) as a future enhancement.

---

## Member 3: Frontend Developer (Web Dashboard)

- **Prototype Responsibilities:**
    - Lead the development of the **web-based dashboard for officials**.
    - Integrate a mapping library (like Leaflet) to visualize hazard reports.
    - Fetch data from the `GET /api/reports` endpoint and display it as markers on the map.
    - Implement basic filtering options (e.g., by hazard type, date).

- **Presentation Responsibilities:**
    - **Slide 2: Technical Approach:** Provide screenshots or a short video of the working dashboard prototype. Explain the frontend technologies used (React, mapping libraries).

---

## Member 4: AI & Data Engineer

- **Prototype Responsibilities:**
    - Develop the simplified **social media listening script**.
    - Connect to a social media API (e.g., Twitter) to fetch posts based on keywords.
    - Process the fetched data and store it in the database with the source as 'SocialMedia'.

- **Presentation Responsibilities:**
    - **Slide 2: Technical Approach:** Own the explanation of the data pipeline. Create a diagram showing how data flows from citizens and social media to the dashboard. Explain the role of AI/ML in the system (even if simplified for the prototype).
    - **Slide 5: Research and References:** Compile the technical references and research papers related to data processing, AI for disaster management, and social media analytics.

---

## Member 5: UX/UI Designer & Accessibility Lead

- **Prototype Responsibilities:**
    - Design the user interface for both the citizen reporting web app and the official's dashboard.
    - Create mockups and a clear design system for the frontend developers to follow.
    - Ensure the prototype is intuitive and easy to navigate.

- **Presentation Responsibilities:**
    - **Overall Design:** Design the presentation template to be visually appealing and professional.
    - **Slide 4: Impact and Benefits:** Lead the content for this slide, focusing on the user-centric benefits and the positive impact on the target audience (citizens, officials).
    - **Visuals:** Create any necessary graphics, icons, or diagrams for the presentation.

---

## Member 6: QA & Community Outreach Lead

- **Prototype Responsibilities:**
    - Conduct thorough testing of the entire prototype (backend APIs, reporting app, and dashboard).
    - Identify and document bugs and usability issues.
    - Verify that the data flow is working as expected.

- **Presentation Responsibilities:**
    - **Slide 3: Feasibility and Viability:** Take the lead on this slide. Identify potential challenges (e.g., data reliability, digital divide, user adoption) and present the mitigation strategies outlined in the project documents.
    - **Slide 4: Impact and Benefits:** Contribute to this slide by detailing the social and community-level benefits of the platform.
    - **Slide 5: Research and References:** Compile references related to community-based disaster management, user adoption strategies, and similar existing platforms.
