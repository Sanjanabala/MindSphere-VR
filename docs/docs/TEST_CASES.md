# MindSphere-VR — Sample Data and Test Cases

## 1. Purpose

This document defines functional test cases for authentication, consent, anxiety assessment, VR exposure, safety controls, session reporting, data storage, and progress monitoring.

## 2. Sample Session Data

The following is fictional sample data for development and testing only.

```json
[
  {
    "sessionId": "TEST-001",
    "userId": "USER-001",
    "scenario": "Accident / Traffic",
    "preAnxiety": 7,
    "peakAnxiety": 8,
    "postAnxiety": 4,
    "exposureLevelReached": 3,
    "pauseCount": 1,
    "durationSeconds": 512,
    "feedback": "Challenging"
  },
  {
    "sessionId": "TEST-002",
    "userId": "USER-001",
    "scenario": "Elevator / Confined Space",
    "preAnxiety": 5,
    "peakAnxiety": 6,
    "postAnxiety": 3,
    "exposureLevelReached": 2,
    "pauseCount": 0,
    "durationSeconds": 360,
    "feedback": "Comfortable"
  }
]
```

## 3. Functional Test Cases

| ID | Test | Expected result |
|---|---|---|
| TC-01 | Register with valid details | Account is created |
| TC-02 | Register with an existing email | Duplicate registration is rejected |
| TC-03 | Login with valid credentials | User dashboard opens |
| TC-04 | Login with invalid credentials | Appropriate error appears |
| TC-05 | Attempt therapy without consent | Therapy access remains blocked |
| TC-06 | Submit pre-session anxiety | Rating is stored |
| TC-07 | Select accident scenario | Traffic environment loads |
| TC-08 | Select confined-space scenario | Elevator environment loads |
| TC-09 | Change exposure level | Relevant environmental properties change |
| TC-10 | Submit anxiety rating of 7 | Environment reduces intensity according to the configured rule |
| TC-11 | Submit anxiety rating of 9 | Exposure pauses and calming support appears |
| TC-12 | Select the calming environment | Calming scene loads |
| TC-13 | End a session | Post-session assessment appears |
| TC-14 | Complete a session report | Correct session values are displayed |
| TC-15 | Refresh session history | Saved records remain available |
| TC-16 | Open progress dashboard | Charts use stored session data |
| TC-17 | Access another user's records without permission | Access is denied |
| TC-18 | Open clinician dashboard | Only authorized records are visible |

## 4. Example Algorithm Tests

### Low anxiety

Input: `3`

Expected: Continue at a comfortable exposure level. Increase exposure only when appropriate and permitted by the session rules.

### Moderate anxiety

Input: `5`

Expected: Maintain exposure and offer supportive guidance.

### High anxiety

Input: `7`

Expected: Reduce environmental intensity and offer calming guidance.

### Very high anxiety

Input: `9`

Expected: Pause exposure and display the safety interface.

### User stop request

Input: User selects "End Session".

Expected: Stop exposure, safely complete the session workflow, and collect a post-session rating when appropriate.

## 5. Report Calculation Tests

For a session with:

- Starting anxiety: 7
- Peak anxiety: 8
- Ending anxiety: 4

Expected reported anxiety change:

`Ending anxiety - Starting anxiety = 4 - 7 = -3 points`

The report should display a decrease of 3 points in the user's reported anxiety. This does not by itself establish clinical improvement.

## 6. Test Execution Record

For each test, record:

- Test ID
- Date
- Environment
- Expected result
- Actual result
- Status: Pass / Fail / Not Tested
- Notes

## 7. Acceptance Criteria

The application is ready for a demonstration when the core user journey works, session data persists correctly, exposure changes affect the selected environment, safety controls function, reports show accurate values, and unauthorized data access is prevented.
