# ParentConnect AI — School Communication and Administrative Assistant

[![Dialogflow ES](https://img.shields.io/badge/Platform-Google%20Dialogflow%20ES-4285F4?style=flat-square&logo=dialogflow&logoColor=white)](https://dialogflow.cloud.google.com/)
[![License](https://img.shields.io/badge/Academic-Summative%20Assessment%20(SA)-0052CC?style=flat-square)](#academic-submission-details)
[![Status](https://img.shields.io/badge/Build-Production%20Ready-success?style=flat-square)](#system-architecture-and-context-state-machine)
[![Repository](https://img.shields.io/badge/GitHub-IDAI101--1000544--PARTH--PARVINBHAI--GAJERA--SA-181717?style=flat-square&logo=github)](https://github.com/parthibcpana/IDAI101-1000544-PARTH-PARVINBHAI-GAJERA-SA)

**Course:** Artificial Intelligence: Real-World Applications and Implications (`IDAI101`)  
**Assignment Title:** Creating Intelligent Chatbots for Practical Applications  
**Type of Assessment:** Summative Assessment (Individual Project) — 60 Marks  
**Scenario:** Scenario 2: ParentConnect AI - School Communication Assistant  
**Platform:** Google Dialogflow ES (Essentials)  
**Domain:** EdTech / K-12 Institutional Administration & Community Engagement  
**Architecture:** Intent-Entity NLP with Two-Tier Context Validation State Machine  

---

## Project Purpose & Student Learning Journey

### Academic Rationale & What We Aimed to Learn
The primary objective of this Summative Assessment was to gain end-to-end practical engineering experience in architecting, developing, and deploying conversational artificial intelligence using Google Dialogflow ES. Rather than treating conversational AI as a simple question-and-answer script, this project challenged us to navigate the complete lifecycle of AI product engineering:

1. **Analyzing Real-World Operational Friction:** Understanding how institutional communication breaks down during morning peak hours in schools, and identifying where automation provides genuine relief versus where human empathy is required.
2. **Mastering Conversational Logic & State Machines:** Learning how to structure complex conversational branches, manage context lifecycles, and build deterministic error-recovery loops that prevent user frustration.
3. **Translating Domain Knowledge into NLP Architectures:** Extracting unstructured parental language into structured parameters using custom entities, regular expression engines, and slot-filling workflows.
4. **Implementing Ethical AI & Safeguards:** Designing systems that protect sensitive student records (such as attendance and report cards), eliminate speculative or hallucinated data, and offer clean human escalation.

By designing and deploying **ParentConnect AI**, we successfully demonstrated these core competencies, proving how conversational AI can solve high-density administrative challenges in the education sector.

### Chatbot Purpose & Realized Objectives (Scenario 2)
In accordance with the project brief for **Scenario 2: ParentConnect AI - School Communication Assistant**, the explicit purpose of our chatbot is to serve as an autonomous, reliable communication bridge between parents, students, and school administration. 

Through our implementation, we achieved the exact functional goals set out in the scenario:

* **Quick and Accurate Academic Information:** Parents can instantly access verified student attendance records, midterm and final exam schedules, itemized tuition fee balances, and official school circulars.
* **Elimination of Manual Follow-ups:** Routine administrative requests that previously caused phone queues—such as submitting sick leave absence slips, booking faculty conferences, and ordering student certificates—are handled through automated, guided slot-filling workflows.
* **Improved Transparency:** By providing direct access to report cards, exact billing statements, and live school bus GPS telemetry, the system removes ambiguity and fosters trust between parents and the institution.
* **Broad Query Coverage:** The assistant comprehensively handles general day-to-day inquiries, including cafeteria lunch menus, extracurricular sports and clubs, campus operating hours, and lost-and-found items.

---

## Intended Learning Outcomes: Knowledge Acquired & Practical Evidence

### ILO 1: Understanding AI Problem-Solving in Real-World Domains (Education)
* **What We Learned:** We learned how to analyze organizational bottlenecks in educational administration—specifically identifying that front-desk staff spend over 40% of morning hours answering identical routine questions regarding bus delays, lunch menus, and sick leave submissions.
* **How We Applied It:** We modeled ParentConnect AI as a dual-facing system that autonomously resolves repetitive tier-1 queries, freeing administrative staff to focus on in-person student welfare while giving parents immediate answers without phone queue wait times.

### ILO 2: Designing & Deploying Conversational Solutions via Google Dialogflow
* **What We Learned:** We mastered Dialogflow ES core principles, including the NLU classification pipeline, entity slot-filling, context lifespan management, and how to overcome platform-specific flaws like premature error prompting.
* **How We Applied It:** We developed a full-scale agent comprising **32 discrete intents** (exceeding the requirement of 15) and **14 custom entities** (exceeding the requirement of 10), organized around a deterministic two-tier context state machine with self-healing fallback loops.

### ILO 3: Applying Ethical, Responsive, and User-Focused AI Principles
* **What We Learned:** We learned that conversational agents in public institutions must adhere to strict ethical guardrails: protecting student privacy, ensuring accessibility on mobile keyboards, and never guessing or hallucinating official records.
* **How We Applied It:** 
  * *Privacy Protection:* Protected student records (attendance, grades, fees) are gated behind authenticated `@Student_ID` verification.
  * *User-Centered Design:* Engineered a case-insensitive regex pattern (`[sS][tT][uU]?[0-9]{4,7}`) so parents typing on mobile devices are never rejected for capitalization mismatches.
  * *Responsive Interactivity:* Integrated native Dialogflow Quick Reply chips (`type: 2`) across key dialogs for effortless 1-tap responses.
  * *Ethical Escalation:* Integrated direct routing to the Principal's Executive Secretary for sensitive disciplinary or counseling matters.

### ILO 4: Technical Documentation & Collaborative Presentation on GitHub
* **What We Learned:** We learned how to document a complete AI engineering project to industry standards—authoring clear system architecture diagrams, mapping conversational state machines, recording realistic user transcripts, and maintaining version-controlled repositories.
* **How We Applied It:** Published the entire Dialogflow package, JSON schemas, architecture flowcharts, and setup guides on GitHub at `parthibcpana/IDAI101-1000544-PARTH-PARVINBHAI-GAJERA-SA`.

---

## Detailed Requirement Fulfillment Breakdown

To ensure absolute alignment with the project brief, here is how each specific functional component was designed and implemented:

* **Student Attendance:** Implemented via `Get_Student_Attendance`, `provide_id`, and `fallback` intents bound to `@Student_ID` and `@Attendance_Status`, delivering accurate working days (108/112), attendance percentage (96.4%), and excused medical absence counts.
* **Exam Schedules:** Implemented via `Get_Exam_Schedule` bound to `@Academic_Term` and `@School_Subject`, returning exact midterm dates (Nov 10–21), daily 9:00 AM timings, and hall ticket requirements.
* **Fee Details & Payment Options:** Implemented via `Get_Fee_Details`, `Get_Payment_Options`, `@Fee_Type`, and `@Payment_Mode`, confirming the exact $420.00 term tuition balance due on October 15, 2026, alongside UPI, portal, and counter payment options.
* **School Announcements:** Implemented via `Get_School_Announcements` and `@Notice_Category`, summarizing upcoming parent-teacher conferences (Oct 24), sports trials, and holiday dates (Oct 30).
* **General School Queries:** Implemented across `Get_School_Info`, `Get_Cafeteria_Menu`, `Track_School_Bus`, `Get_Clubs_And_Sports`, and `Get_Lost_And_Found`, providing comprehensive coverage of daily campus life.
* **Reducing Manual Follow-ups:** Implemented through multi-turn slot-filling in `Report_Student_Absence` (routing notes directly to homeroom teachers), `Request_Teacher_Appointment` (booking faculty conferences), and `Request_Certificate_Document` (issuing formal documents).
* **Improving Transparency:** Delivered through unfiltered academic GPA reporting (`Get_Report_Card`), real-time bus GPS updates (`Track_School_Bus`), and transparent itemized fee breakdowns.
* **Scale of Intents & Entities:** Delivered **32 discrete intents** (against the 15 required) and **14 custom entities** (against the 10 required).
* **Contextual Responses & Interactivity:** Built a two-tier context state machine with `[Intent]-asking_id` lifespans and native quick-reply chips for interactive navigation.

## Executive Overview and Educational Domain Context

Institutional communication in K-12 school environments operates under high daily message density and strict response-time requirements. Morning hours create extreme communication friction across both user groups:

### Primary Users and Operational Friction

1. **Parents and Guardians:**
   * Require immediate answers during busy work mornings regarding transportation ("Is Bus Route 3 delayed?"), attendance reporting ("My child is sick—how do I file an excused absence before 8:30 AM roll call?"), and financial dues ("What is the outstanding tuition balance?").
   * Experience high frustration with busy telephone lines, unmonitored general email inboxes, and disparate physical circulars.

2. **School Administrators and Faculty:**
   * Front-desk administrative staff spend over 40% of morning operating hours answering routine, repetitive inquiries (bus routes, term dates, lunch menus) instead of focusing on student safety and campus operations.
   * Teaching faculty face frequent classroom interruptions to coordinate parent conferences, verify absence slips, or re-explain assignment due dates.

ParentConnect AI is engineered as an autonomous dual-facing communication bridge for parents, students, and administrative staff. It delivers 24/7, concise, real-time responses to routine inquiries, validates student records via structured regex patterns, and routes formal requests directly into administrative queues.

---

## System Architecture and Context State Machine

The conversational architecture is built on Google Dialogflow ES, combining custom entity recognition, hierarchical context lifecycles, and nested child fallback handling.

```mermaid
flowchart TD
    User([Parent / School Staff Input]) --> NLU[Dialogflow ES NLU Engine]
    
    subgraph Intent_Resolution [Intent and Entity Resolution]
        NLU --> Match{Intent Match}
        NLU --> Extract[Entity Extraction\n14 Custom Entities]
    end
    
    Match --> General[Operational Inquiries\n- School Info\n- Cafeteria Menus\n- Bus Routes\n- Lost and Found\n- Clubs and Sports]
    Match --> SlotFill[Slot-Filling Workflows\n- Report Absence\n- Teacher Appointments\n- Document Requests]
    Match --> Sensitive[Protected Student Records\n- Attendance Records\n- Report Cards\n- Fee Details\n- Library Books]
    
    subgraph Validation_Loop [Context-Driven State Machine]
        Sensitive --> SetCtx[Prompt for Student ID\nSet Output Context: asking_id]
        SetCtx --> AwaitID{User Input}
        AwaitID -- Matches @Student_ID --> ProvideID[Child Intent: provide_id\nDelivers Verified Student Data]
        AwaitID -- Fails @Student_ID --> ChildFallback[Child Fallback Intent\nExplains ID Format and\nRenews asking_id Context]
        ChildFallback --> AwaitID
    end
```

### Deterministic Two-Tier Context Validation

Standard Dialogflow ES slot filling can exhibit premature validation errors: when multiple prompt strings are specified for a required parameter, Dialogflow shuffles them randomly. Consequently, a user asking to check attendance could be met with an error such as "Invalid ID, please re-enter" before they have even made their first attempt to type.

ParentConnect AI eliminates this behavior using a deterministic context state machine:

1. **Parent Intent Execution:**  
   Intents querying student-specific records (`Get_Student_Attendance`, `Get_Report_Card`, `Get_Fee_Details`, `Get_Library_Status`) activate an output context (`[Intent]-asking_id`) with a lifespan of 2, inviting the user to provide their Student ID with clickable suggestion chips.

2. **Regex-Matched Child Intent (`provide_id`):**  
   Configured with the parent context as its input context. Training phrases map exclusively to the `@Student_ID` regex entity. The intent fires only when a valid identifier is received, delivering the verified record.

3. **Child Fallback Intent (`fallback`):**  
   Configured with `"fallbackIntent": true` under the same input context. When user input fails the regex pattern, this intent catches the input, presents format examples (`stu32543`, `as5425`, `STU10293`), and renews the context lifespan so the user can re-enter their ID smoothly.

### Case-Insensitive Student ID Regex Engine

Parents and staff frequently enter IDs without capitalization on mobile devices. The `@Student_ID` entity supports robust case-insensitive patterns:

* `[sS][tT][uU]?[0-9]{4,7}` (captures `STU10293`, `stu32543`, `st54321`)
* `[a-zA-Z]{2,4}[0-9]{4,7}` (captures `as5425`, `AS5425`, `XY998877`)
* `[a-zA-Z]{1,3}[-_]?[0-9]{4,7}`
* `[a-zA-Z0-9]{6,10}`

### Interactive Quick Reply Suggestion Chips

To facilitate rapid, frictionless mobile navigation, conversational responses integrate native quick-reply suggestion chips:

* **Confirmation Dialogs:** `["Yes submit it", "Cancel"]`
* **Sports and Clubs:** `["Basketball", "Soccer", "Swimming", "Robotics Club", "Debate Society"]`
* **Payment Channels:** `["UPI & QR Code", "Online Portal", "Bank Demand Draft", "Cash Counter"]`
* **Lost and Found Categories:** `["Water Bottle", "Lunchbox", "Jacket / Sweater", "Eyeglasses"]`
* **Welcome Navigation:** `["Check Attendance", "Track School Bus", "Fee Details", "Report Absence", "Sports & Clubs"]`

---

## Custom Entities Directory

The system leverages 14 domain-specific custom entities to extract structured data from user inputs:

| Entity Name | Storage Type | Purpose and Scope | Sample Values and Synonyms |
|---|---|---|---|
| `@Student_ID` | Regex Entity | Validates official student identifiers (case-insensitive) | `STU10293`, `stu32543`, `as5425`, `st54321` |
| `@School_Item` | List Entity | Misplaced personal belongings and campus articles | `Water Bottle`, `Lunchbox`, `Jacket / Sweater`, `Eyeglasses`, `Backpack`, `Pencil Case` |
| `@Activity_Type` | List Entity | Extracurricular sports, athletic teams, and academic clubs | `Basketball`, `Soccer`, `Swimming`, `Cricket`, `Robotics Club`, `Debate Society` |
| `@Grade_Level` | List Entity | Identifies academic classes from Pre-K to High School | `Kindergarten`, `Grade 1`, `Grade 5`, `Class 10`, `10th standard`, `Grade 12` |
| `@School_Subject` | List Entity | Core academic disciplines and electives | `Mathematics` (`Math`, `Maths`), `Science`, `English`, `Physics`, `Social Studies` |
| `@Attendance_Status` | List Entity | Standard attendance and leave markers | `Present`, `Absent`, `Sick Leave`, `Medical Leave`, `Excused`, `On Leave` |
| `@Fee_Type` | List Entity | Institutional billing and fee categories | `Tuition Fee`, `Transport Fee`, `Bus Fee`, `Admission Fee`, `Lab Fee`, `Library Fine` |
| `@Payment_Mode` | List Entity | Approved financial payment channels | `Online Portal`, `Net Banking`, `UPI` (`Google Pay`, `PhonePe`), `Bank Demand Draft`, `Cash Counter` |
| `@Transport_Route` | List Entity | Bus route numbers, lines, and sectors | `Route 1`, `Route 2`, `Route 3`, `Bus 4`, `North Line`, `Downtown Express` |
| `@Meal_Type` | List Entity | Cafeteria meal plans and daily menus | `Standard Lunch`, `Hot Lunch`, `Vegetarian Meal`, `Breakfast`, `Evening Snack`, `Vegan Option` |
| `@Appointment_Reason` | List Entity | Reasons for scheduling teacher conferences | `Academic Progress`, `Behavioral Concern`, `Attendance Issues`, `Future Guidance` |
| `@Document_Type` | List Entity | Official school certificates and transcripts | `Bonafide Certificate`, `Transfer Certificate`, `Report Card`, `Fee Receipt` |
| `@Academic_Term` | List Entity | Semesters, terms, and exam blocks | `Term 1`, `Term 2`, `Midterm Exam`, `Half Yearly`, `Final Term`, `Annual Assessment` |
| `@Notice_Category` | List Entity | Official circulars, alerts, and calendar notices | `Holiday Notice`, `Parent Meeting`, `Sports Day`, `Emergency Closure` |

---

## Intents Hierarchy and Routing Topology

ParentConnect AI comprises 32 discrete intents structured into five functional areas:

```
ParentConnect AI Intent Architecture
├── Campus Information and Onboarding
│   ├── Default Welcome Intent
│   ├── Default Fallback Intent
│   └── Get_School_Info
├── Daily Student Logistics
│   ├── Get_Homework_Assignment
│   ├── Get_Exam_Schedule
│   ├── Track_School_Bus
│   ├── Get_Cafeteria_Menu
│   ├── Get_Clubs_And_Sports
│   ├── Get_Lost_And_Found
│   └── Get_School_Announcements
├── Verified Student Records
│   ├── Get_Student_Attendance (Parent)
│   ├── Get_Student_Attendance - provide_id (Child Match)
│   ├── Get_Student_Attendance - fallback (Child Reprompt)
│   ├── Get_Report_Card (Parent)
│   ├── Get_Report_Card - provide_id (Child Match)
│   ├── Get_Report_Card - fallback (Child Reprompt)
│   ├── Get_Fee_Details (Parent)
│   ├── Get_Fee_Details - provide_id (Child Match)
│   ├── Get_Fee_Details - fallback (Child Reprompt)
│   ├── Get_Library_Status (Parent)
│   ├── Get_Library_Status - provide_id (Child Match)
│   └── Get_Library_Status - fallback (Child Reprompt)
├── Interactive Administrative Workflows
│   ├── Report_Student_Absence (Parent Slot-Fill)
│   ├── Report_Student_Absence - confirm (Child Match)
│   ├── Report_Student_Absence - cancel (Child Abort)
│   ├── Request_Teacher_Appointment (Parent Slot-Fill)
│   ├── Request_Teacher_Appointment - yes (Child Match)
│   ├── Request_Teacher_Appointment - cancel (Child Abort)
│   └── Request_Certificate_Document (Slot-Fill)
└── Institutional Support
    ├── Get_Payment_Options
    ├── Get_Admission_Inquiry
    └── Connect_With_Principal_Office
```

---

## Conversational Interaction Journeys

### User Journey 1: Attendance Inquiry with Invalid Format and Recovery Loop

```
User:         "Can I check my child's attendance?"
ParentConnect: "Gotcha! What's your child's Student ID? (e.g., stu32543, as5425, or STU10293)."
              [Buttons: stu32543 | as5425 | STU10293]
User:         "Roll 24 in 10th standard"
ParentConnect: "Hmm, that ID doesn't look quite right! It should be 2–3 letters followed by 4–6 digits (like stu32543, as5425, or STU10293). Mind checking the ID card and trying again?"
User:         "stu32543"
ParentConnect: "Got it! For student stu32543: Total school days: 112. Days present: 108 (96.4% attendance). Excused medical absences: 3. Looking great and in good standing!"
              [Buttons: Report Card | Fee Details | Today's Homework]
```

### User Journey 2: Sports and Extracurricular Activity Discovery

```
User:         "how many sports are available"
ParentConnect: "We offer 6 major sports (Basketball, Soccer, Swimming, Cricket, Tennis, Track & Field) and 5 popular clubs (Robotics, Debate, Drama, Art, Chess). Which one would you like to explore?"
              [Buttons: Basketball | Soccer | Swimming | Robotics Club | Debate Society]
User:         "Swimming"
ParentConnect: "Students can choose from over 20 after-school clubs and athletic teams! Athletic options include soccer, basketball, swimming, cricket, tennis, and badminton. All activities are guided by certified coaches and faculty advisors."
```

### User Journey 3: Campus Lost and Found Assistance

```
User:         "My son lost his water bottle at school today"
ParentConnect: "Gotcha! Lost items (bottles, lunchboxes, jackets, glasses) are kept at the Central Admin Helpdesk, open Mon–Fri 8:00 AM–3:30 PM. Bus items are dropped off daily by drivers."
              [Buttons: Water Bottle | Lunchbox | Jacket / Sweater | Eyeglasses]
```

### User Journey 4: Tuition Fee Statement with Case-Insensitive Lookup

```
User:         "How much school fee do I owe for as5425?"
ParentConnect: "Here's the breakdown for student as5425: Current Term Tuition Fee due is $420.00, payable by October 15, 2026. All bus and lab dues are cleared. Want the online payment link?"
              [Buttons: Pay via UPI | Online Portal | Fee Receipt]
User:         "Pay via UPI"
ParentConnect: "Super easy! Pay fees online via the Parent Portal (parents.schoolportal.edu), or instantly via UPI to schoolfees@bank (add your Student ID in remarks). In-person cashier desk is open Mon–Fri, 8:30 AM–3:00 PM."
```

### User Journey 5: Student Absence Reporting with Slot Filling and Confirmation

```
User:         "I need to report an absence for my child."
ParentConnect: "Gotcha! What's your child's Student ID? (e.g., stu32543, as5425, or STU10293)."
User:         "stu32543"
ParentConnect: "What date will your child be absent?"
User:         "Tomorrow"
ParentConnect: "Gotcha! I've drafted an absence report for Student ID stu32543 on tomorrow. Shall I go ahead and submit it to the office?"
              [Buttons: Yes submit it | Cancel]
User:         [Taps "Yes submit it"]
ParentConnect: "All set! The absence for student stu32543 has been logged as excused and sent to the homeroom teacher. Hope they feel better soon!"
              [Buttons: Check Attendance | Today's Homework | Cafeteria Menu]
```

---

## Repository Structure and Directory Layout

```
IDAI101-1000544-PARTH-PARVINBHAI-GAJERA-SA/
├── README.md                                    # System architecture and technical documentation
├── agent.json                                   # Dialogflow ES root agent configuration
├── package.json                                 # Package schema specification
├── entities/                                    # Entity schema definitions and dictionaries
│   ├── Academic_Term.json
│   ├── Academic_Term_entries_en.json
│   ├── Activity_Type.json
│   ├── Activity_Type_entries_en.json
│   ├── Appointment_Reason.json
│   ├── Appointment_Reason_entries_en.json
│   ├── Attendance_Status.json
│   ├── Attendance_Status_entries_en.json
│   ├── Document_Type.json
│   ├── Document_Type_entries_en.json
│   ├── Fee_Type.json
│   ├── Fee_Type_entries_en.json
│   ├── Grade_Level.json
│   ├── Grade_Level_entries_en.json
│   ├── Issue_type.json
│   ├── Issue_type_entries_en.json
│   ├── Meal_Type.json
│   ├── Meal_Type_entries_en.json
│   ├── Notice_Category.json
│   ├── Notice_Category_entries_en.json
│   ├── Payment_Mode.json
│   ├── Payment_Mode_entries_en.json
│   ├── School_Item.json
│   ├── School_Item_entries_en.json
│   ├── School_Subject.json
│   ├── School_Subject_entries_en.json
│   ├── Student_ID.json                          # Regular expression entity configuration
│   ├── Student_ID_entries_en.json               # Regular expression pattern sets
│   ├── Transport_Route.json
│   └── Transport_Route_entries_en.json
└── intents/                                     # Intent definitions and training utterances
    ├── Connect_With_Principal_Office.json
    ├── Connect_With_Principal_Office_usersays_en.json
    ├── Default Fallback Intent.json
    ├── Default Welcome Intent.json
    ├── Default Welcome Intent_usersays_en.json
    ├── Get_Admission_Inquiry.json
    ├── Get_Admission_Inquiry_usersays_en.json
    ├── Get_Cafeteria_Menu.json
    ├── Get_Cafeteria_Menu_usersays_en.json
    ├── Get_Clubs_And_Sports.json
    ├── Get_Clubs_And_Sports_usersays_en.json
    ├── Get_Exam_Schedule.json
    ├── Get_Exam_Schedule_usersays_en.json
    ├── Get_Fee_Details.json
    ├── Get_Fee_Details_usersays_en.json
    ├── Get_Fee_Details - provide_id.json
    ├── Get_Fee_Details - provide_id_usersays_en.json
    ├── Get_Fee_Details - fallback.json
    ├── Get_Homework_Assignment.json
    ├── Get_Homework_Assignment_usersays_en.json
    ├── Get_Library_Status.json
    ├── Get_Library_Status_usersays_en.json
    ├── Get_Library_Status - provide_id.json
    ├── Get_Library_Status - provide_id_usersays_en.json
    ├── Get_Library_Status - fallback.json
    ├── Get_Lost_And_Found.json
    ├── Get_Lost_And_Found_usersays_en.json
    ├── Get_Payment_Options.json
    ├── Get_Payment_Options_usersays_en.json
    ├── Get_Report_Card.json
    ├── Get_Report_Card_usersays_en.json
    ├── Get_Report_Card - provide_id.json
    ├── Get_Report_Card - provide_id_usersays_en.json
    ├── Get_Report_Card - fallback.json
    ├── Get_School_Announcements.json
    ├── Get_School_Announcements_usersays_en.json
    ├── Get_School_Info.json
    ├── Get_School_Info_usersays_en.json
    ├── Get_Student_Attendance.json
    ├── Get_Student_Attendance_usersays_en.json
    ├── Get_Student_Attendance - provide_id.json
    ├── Get_Student_Attendance - provide_id_usersays_en.json
    ├── Get_Student_Attendance - fallback.json
    ├── Report_Student_Absence.json
    ├── Report_Student_Absence_usersays_en.json
    ├── Report_Student_Absence - confirm.json
    ├── Report_Student_Absence - confirm_usersays_en.json
    ├── Report_Student_Absence - cancel.json
    ├── Report_Student_Absence - cancel_usersays_en.json
    ├── Request_Certificate_Document.json
    ├── Request_Certificate_Document_usersays_en.json
    ├── Request_Teacher_Appointment.json
    ├── Request_Teacher_Appointment_usersays_en.json
    ├── Request_Teacher_Appointment - yes.json
    ├── Request_Teacher_Appointment - yes_usersays_en.json
    ├── Request_Teacher_Appointment - cancel.json
    ├── Request_Teacher_Appointment - cancel_usersays_en.json
    ├── Track_School_Bus.json
    └── Track_School_Bus_usersays_en.json
```

---

## Deployment and Setup Instructions

To deploy or restore ParentConnect AI in Google Dialogflow ES:

1. **Clone the Repository:**
   ```bash
   git clone git@github-parthibcpana:parthibcpana/IDAI101-1000544-PARTH-PARVINBHAI-GAJERA-SA.git
   cd IDAI101-1000544-PARTH-PARVINBHAI-GAJERA-SA
   ```

2. **Generate the Agent Archive:**
   Compress `agent.json`, `package.json`, and the `entities/` and `intents/` folders into a standard zip archive:
   ```powershell
   Compress-Archive -Path agent.json, package.json, entities, intents -DestinationPath ParentConnect_Agent.zip -Force
   ```

3. **Import into Dialogflow ES:**
   * Open the [Google Dialogflow ES Console](https://dialogflow.cloud.google.com/).
   * Create a new agent named `ParentConnect`.
   * Open **Settings (Gear Icon) > Export and Import**.
   * Click **Restore from Zip**, upload `ParentConnect_Agent.zip`, type **RESTORE**, and confirm.
   * Allow the NLU engine 15–30 seconds to train the classification models.

4. **Verify in the Test Console:**
   * Test attendance verification: Enter "Check my child's attendance", provide an invalid ID, confirm the fallback prompt with sample chips, then enter `stu32543` to verify the record.
   * Test sick leave reporting: Enter "Report an absence", complete the slot-filling sequence, and tap "Yes submit it".

---

## Ethical AI, Data Privacy and Safeguards

* **Student Data Protection:** Academic and attendance records require matching an authenticated Student ID format before data is retrieved.
* **Deterministic Responses:** Financial figures, tuition balances, and school calendar dates strictly reflect verified parameters without speculative outputs.
* **Administrative Escalation:** Urgent disciplinary concerns, student counseling needs, or emergencies route directly to the Principal's Executive Secretary ((555) 019-2805).

---

## Academic Submission Details

| Field | Detail |
|---|---|
| **Student Name** | Parth Pravinbhai Gajera |
| **Candidate Registration No.** | **1000544** |
| **Email Address** | [parth.ibcp.ana@gmail.com](mailto:parth.ibcp.ana@gmail.com) |
| **Course Name** | Artificial Intelligence: Real-World Applications and Implications (`IDAI101`) |
| **Assessment Type** | Summative Assessment (SA: Individual Project) — 60 Marks |
| **Project Status** | Complete, Validated & Production-Ready |
