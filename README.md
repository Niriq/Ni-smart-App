# SMART on FHIR Patient Health App

## Project Overview

This project is a patient-facing web application built using SMART on FHIR and FHIR R4.

The application allows a patient to securely sign in through a SMART Health IT sandbox and view their demographic information and selected clinical observations.

The project demonstrates healthcare interoperability, FHIR API integration, OAuth 2.0 authorization, and patient-specific data retrieval.

## Features

- SMART on FHIR patient authentication
- OAuth 2.0 authorization
- FHIR R4 integration
- Patient demographic retrieval
- Patient-specific Observation searches
- Height display
- Blood pressure display
- HDL cholesterol display
- LDL cholesterol display
- Observation dates and measurement units
- Missing-data and error handling
- Responsive HTML interface

## Technologies Used

| Technology | Purpose |
|---|---|
| HTML5 | Application structure |
| CSS3 | Responsive styling |
| JavaScript | Application logic |
| SMART on FHIR | Healthcare authorization |
| FHIR R4 | Healthcare data exchange |
| fhirclient 3.0.1 | SMART authorization and FHIR requests |
| GitHub Pages | Static application hosting |
| SMART Health IT Sandbox | Test patient records |

## FHIR Resources

The application reads two FHIR resource types:

### Patient

Used to retrieve:
- Patient name
- Gender
- Birth date

Age is calculated from the patient's birth date.

### Observation

Used to retrieve selected clinical measurements:

| Measurement | LOINC Code |
|---|---|
| Height | 8302-2 |
| Blood pressure panel | 85354-9 |
| Systolic blood pressure | 8480-6 |
| Diastolic blood pressure | 8462-4 |
| HDL cholesterol | 2085-9 |
| LDL cholesterol | 13457-7 |

## SMART Authorization Scopes

The application requests:

- `launch/patient`
- `openid`
- `fhirUser`
- `patient/Patient.read`
- `patient/Observation.read`

The application uses read-only access and does not create, update, or delete patient records.

## Application Workflow

1. Patient opens the application.
2. Patient selects Sign in.
3. SMART authorization redirects the patient to the sandbox.
4. Patient authorizes access.
5. The application receives the authorized FHIR client session.
6. The application retrieves the signed-in patient's demographics.
7. The application searches for selected observations.
8. Results are displayed in the patient interface.

## Project Structure

| File | Purpose |
|---|---|
| `index.html` | Patient dashboard and OAuth redirect target |
| `launch.html` | SMART patient authorization |
| `health.html` | Static hosting health check |
| `.nojekyll` | GitHub Pages configuration |
| `README.md` | Project documentation |

## Testing

The application can be tested using the SMART Health IT R4 sandbox.

Testing should include:
- Successful patient authorization
- Patient demographic retrieval
- Observation retrieval
- Missing observation handling
- Sign-out functionality
- Mobile-friendly display

## Live Application

[Open the SMART Patient App](https://niriq.github.io/Ni-smart-App/)

## Project Goals

This project demonstrates practical knowledge of:

- Healthcare interoperability
- Electronic Medical Record (EMR) data structures
- HL7 FHIR standards
- SMART on FHIR authorization
- REST API requests
- Clinical terminology and LOINC codes
- Patient data access and presentation

Built as a healthcare IT portfolio project.
