# AI Log - Task 2 (App Workflow and System Model)

## Student Scope
- Assignment part: Task 2 - App behavior understanding and system model.
- Owner: Member #2.
- Date: 2026-03-28.

## Objective
Document how the APK works (MainActivity, Login, Profile), identify key assets and data flows, and produce a simple system model diagram and text for the report/presentation.

## Interaction Records

### Record 1 - Define Task 2 deliverables
- User prompt summary: "I am member #2. Help only with #2 content."
- AI output summary:
  - Suggested Task 2 outputs: app summary, system model, assets/data flows, assumptions/goals.
  - Provided report-ready text blocks.
- Human validation:
  - Confirmed this matches team split document (member #2 is workflow + system model owner).
- Decision:
  - Accepted.

### Record 2 - Build app workflow from static evidence
- User prompt summary: Request for content focused on #2 only.
- AI output summary:
  - Workflow drafted:
    1) MainActivity collects username/password and saves to `credentials.txt`.
    2) Login reads `credentials.txt` and verifies input.
    3) On success, app creates `sessionToken` and stores in `SharedPreferences` (`SessionPrefs`).
    4) Profile can clear session token (logout).
- Human validation:
  - Cross-checked against decompiled method names and call flow evidence.
- Decision:
  - Accepted.

### Record 3 - Generate system model diagram (Mermaid)
- User prompt summary: "How to export the image?"
- AI output summary:
  - Provided Mermaid diagram with components and arrows.
  - Provided export methods (Mermaid Live / VS Code preview / draw.io).
- Human validation:
  - Diagram opened in local `model.md`.
- Decision:
  - Accepted.

### Record 4 - Fix Mermaid rendering issue
- User prompt summary: "Second line not showing in node label."
- AI output summary:
  - Updated label line break from plain long text to `<br>` format.
  - Updated file `model.md`.
- Human validation:
  - Node label readability improved in preview.
- Decision:
  - Accepted.

### Record 5 - Confirm if diagram is valid system model
- User prompt summary: "Is this the system model figure?"
- AI output summary:
  - Confirmed yes; includes components, assets, and data flow.
  - Suggested adding 2-3 explanatory lines under the figure.
- Human validation:
  - Matches rubric expectation for Task 2.
- Decision:
  - Accepted.

## Key Evidence Used for Task 2 Claims
- Package and activities: `com.example.mastg_test0016`, `MainActivity`, `Login`, `Profile`.
- Storage evidence:
  - `MainActivity.saveCredentialsToFile(...)` writes `credentials.txt`.
  - `Login.checkCredentials(...)` reads `credentials.txt`.
  - `Login.createSession()` stores `sessionToken` in `SharedPreferences` (`SessionPrefs`).
  - `Profile.clearSession()` removes `sessionToken`.

## Final Content Delivered by AI for Task 2
- App summary paragraph (3-5 sentences).
- System model diagram (Mermaid).
- Assets and data-flow description.
- Basic attacker assumptions/goals text for model section.

## Limitations
- Analysis is static (no emulator runtime trace in this log).
- Dynamic behavior should be validated separately if required by tutor.
