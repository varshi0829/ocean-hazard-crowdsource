# Suggested New Features & Implementation Steps

This document outlines new features that can be added to the platform to enhance its capabilities, along with the steps required to implement them.

---

### 1. Peer Verification ("I See This Too" Button)

*   **Feature Description:** Allows users to corroborate a report submitted by someone else by clicking a confirmation button. This helps build a trust score for each report.
*   **Value:** Crowdsources the verification process, helping officials quickly identify legitimate and urgent reports.

#### Implementation Steps:
1.  **Backend (Database):** Add a `confirmations` field (Integer) to the `reports` database schema.
2.  **Backend (API):** Create a new API endpoint: `POST /api/reports/:id/confirm`. This endpoint will increment the `confirmations` counter for the specified report ID.
3.  **Frontend (Citizen App):** On the screen where a user views a report, add an "I See This Too" button. When clicked, it should call the new API endpoint and then become disabled to prevent multiple confirmations from the same user.
4.  **Frontend (Official Dashboard):** Display the confirmation count next to each report. Consider using this count to visually highlight more credible reports (e.g., by changing the color or size of the map pin).

---

### 2. AI-Powered Hotspot Summarization

*   **Feature Description:** When a "hotspot" (a dense cluster of reports) is identified, use an AI model to automatically generate a one-sentence summary of the situation.
*   **Value:** Saves officials critical time by providing an instant overview of a developing situation instead of requiring them to read every single report.

#### Implementation Steps:
1.  **Backend (Algorithm):** Develop a hotspot detection algorithm. This can be a script that runs periodically, clustering reports based on geographic proximity and time.
2.  **Backend (AI Integration):** When a hotspot is detected, collect the `description` text from all reports within it.
3.  **Backend (API Call):** Send the collected text to a generative AI API (like the Gemini API) with a clear prompt, such as: `"Summarize these user reports from a coastal disaster into a single, concise sentence: [TEXTS]"`.
4.  **Backend (Database):** Store the AI-generated summary in association with the hotspot data.
5.  **Frontend (Official Dashboard):** When displaying a hotspot on the map, show the generated summary in a tooltip or sidebar.

---

### 3. SMS Reporting Gateway

*   **Feature Description:** Allows any user to submit a hazard report via a simple SMS text message, without needing a smartphone or internet connection.
*   **Value:** Massively increases the accessibility of the platform, ensuring that the most vulnerable populations can contribute reports. This is a critical feature for equity and comprehensive data gathering.

#### Implementation Steps:
1.  **Service Integration:** Sign up for a third-party SMS gateway service (e.g., Twilio, Vonage) and acquire a phone number.
2.  **Backend (API):** Create a new webhook endpoint in your application: `POST /api/sms-report`.
3.  **Service Configuration:** Configure your SMS service to send an HTTP POST request to your new endpoint whenever it receives an SMS message.
4.  **Backend (Parsing Logic):** In the `/api/sms-report` endpoint, write logic to parse the body of the incoming SMS. Define a simple format for users, such as `HAZARD_CODE @ Location Description` (e.g., `FLOOD @ Main Market Road`).
5.  **Backend (Database):** After parsing the hazard and location, create a new report in your database with the `source` field set to `'SMS'`.
6.  **Community Outreach:** Publicize the phone number and the simple reporting format to coastal communities.
