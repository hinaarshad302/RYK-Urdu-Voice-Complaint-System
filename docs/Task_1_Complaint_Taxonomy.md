# Task 1: Problem Definition and Complaint Taxonomy Design

## Project
**RYK Urdu Voice Complaint Routing System for Campus and Community Services**

## 1. Problem Definition
University students and staff may report problems through phone calls, paper registers, or WhatsApp messages. These reports can be delayed, misplaced, sent to the wrong department, or difficult to track. Students who prefer speaking Urdu may also face difficulty when complaint processes rely on written forms.

This project proposes a voice-based system in which a user can speak an Urdu complaint. The system converts speech into text, identifies the complaint category, and forwards it to the relevant university department for staff review and action.

## 2. Initial Project Scope
The first prototype is designed for a university in Rahim Yar Khan and includes:
- University academic and administrative services
- Hostel services
- University transport services

The target university has not yet been specified. Department names and responsibilities in this document are proposed examples and must be checked against the selected university before deployment.

## 3. Project Objectives
1. Accept a spoken Urdu complaint.
2. Convert the audio into text using an Urdu-capable speech-to-text model.
3. Classify the complaint into a predefined category.
4. Identify the relevant department using a configurable routing matrix.
5. Assign a complaint reference ID and save the complaint.
6. Provide an admin interface for staff to review and update complaint status.
7. Send unclear or low-confidence complaints for manual review.

## 4. Complaint Taxonomy and Routing Matrix

| ID | Complaint Category | Example Issue | Proposed Department |
|---|---|---|---|
| C01 | Electricity | Lights, fans, power supply | Electrical / Maintenance |
| C02 | Water Supply | No water, water leakage | Maintenance |
| C03 | Cleanliness | Dirty classrooms, washrooms | Sanitation / Cleaning |
| C04 | IT and Computer Lab | Computers, internet, lab equipment | IT Department |
| C05 | Classroom Facilities | Broken desks, damaged furniture | Maintenance |
| C06 | Fee and Accounts | Fee submission, receipts, dues | Accounts Office |
| C07 | Admission and Registration | Admission or registration record | Admissions Office |
| C08 | Examination | Date sheet, exam record, result issue | Examination Department |
| C09 | Library | Books, library access, facilities | Library |
| C10 | Hostel | Room, mess, water, hostel maintenance | Hostel Administration |
| C11 | Transport | Bus route, timing, vehicle issue | Transport Office |
| C12 | Security | Access control or campus safety concern | Security Office |
| C13 | Other / Unclear | Complaint does not match a category | Admin Review |

**Routing note:** These are prototype categories and proposed destinations. Confirm the actual office names, reporting process, and responsibilities with the selected university.

## 5. Sample Urdu Complaint Scenarios

| Sample ID | Urdu Complaint | Expected Category | Proposed Department |
|---|---|---|---|
| S01 | کمپیوٹر لیب میں کمپیوٹر کام نہیں کر رہے۔ | IT and Computer Lab | IT Department |
| S02 | ہمارے ہاسٹل کے کمرے میں پانی نہیں آ رہا۔ | Hostel | Hostel Administration |
| S03 | یونیورسٹی بس روزانہ دیر سے آتی ہے۔ | Transport | Transport Office |
| S04 | میں نے فیس جمع کروا دی ہے لیکن رسید نہیں ملی۔ | Fee and Accounts | Accounts Office |
| S05 | کلاس روم کے پنکھے خراب ہیں۔ | Electricity / Facilities | Electrical / Maintenance |
| S06 | واش رومز کی صفائی نہیں ہو رہی۔ | Cleanliness | Sanitation / Cleaning |
| S07 | لائبریری میں مطلوبہ کتاب دستیاب نہیں۔ | Library | Library |
| S08 | امتحان کے ریکارڈ میں میرا نام درست نہیں ہے۔ | Examination | Examination Department |

These are synthetic examples prepared for prototype testing. They are not collected complaints from a real university.

## 6. Priority Levels
- **Low:** General suggestion or non-urgent request.
- **Medium:** Routine service issue that needs attention.
- **High:** Significant disruption to study, hostel living, or transport.
- **Urgent:** Potential immediate safety or security concern requiring prompt human attention.

The prototype does not replace emergency services or automatically dispatch emergency responders. Urgent complaints must be flagged for human review according to the university's actual procedures.

## 7. Proposed System Workflow
1. User records and submits an Urdu voice complaint.
2. System checks that an audio file was received.
3. Speech-to-text module generates a transcript.
4. Classification module predicts a complaint category.
5. Routing rules select the proposed department.
6. System assigns a unique complaint ID and saves the record.
7. Admin dashboard displays the complaint for staff review.
8. Authorized staff update the status and handle the complaint.

## 8. Unclear Complaint Handling
If the transcript is empty, unclear, or does not confidently match a category:
- Do not silently route it to an unrelated department.
- Mark it as **Needs Review**.
- Send it to **Admin Review**.
- Keep the available transcript and complaint record for authorized review.
- Allow an authorized staff member to select the correct category and department.

## 9. Initial Functional Requirements
- FR-01: The user can submit an Urdu audio complaint.
- FR-02: The system can produce and store a text transcript.
- FR-03: The system can classify a complaint using the defined taxonomy.
- FR-04: The system can map a category to a configured department.
- FR-05: The system can generate a unique complaint reference ID.
- FR-06: Admin staff can view complaints.
- FR-07: Admin staff can update complaint status.
- FR-08: Unclear complaints can be flagged for manual review.

## 10. Initial Non-Functional Requirements
- The interface should be simple and usable by non-technical users.
- Complaint records should be stored consistently.
- Access to complaint details should be restricted to authorized users.
- The system should handle Urdu text correctly.
- Errors in transcription or classification should be visible and recoverable.
- The prototype should be tested with different Urdu speaking styles and recording conditions.

## 11. Proposed Technology Stack
- Backend: Python and FastAPI
- Speech-to-text: Whisper
- Classification: NLP with rule-based and AI-assisted logic
- Frontend: React and JavaScript
- Database: SQLite for the initial prototype; PostgreSQL can be considered later
- Version control: Git and GitHub

## 12. Task 1 Deliverables
- Problem definition
- Initial complaint taxonomy
- Proposed department routing matrix
- Synthetic Urdu complaint scenarios for testing
- Initial functional and non-functional requirements

## 13. Open Decisions Before a Real University Pilot
- Confirm the selected university.
- Verify its actual department names and responsibilities.
- Confirm who is authorized to view and update complaints.
- Agree on the real complaint status workflow and escalation procedure.
- Obtain permission before collecting or using real student complaint recordings.

---
**Document status:** Initial prototype design. Department routing and sample scenarios require validation with the selected university.
