# MindSphere-VR
AI-assisted VR exposure therapy platform with adaptive anxiety monitoring and session tracking.
# MindSphere-VR

### AI-Assisted Virtual Reality Exposure Therapy for PTSD and Anxiety Management

## Overview

MindSphere-VR is a virtual reality-based platform designed to provide immersive, controlled exposure experiences with adaptive support and anxiety tracking. It combines realistic 3D environments, user-reported anxiety assessments, gradual exposure control, breathing guidance, and session analytics in a unified web application.

The platform focuses on accident-related PTSD triggers and confined-space anxiety, with a calming environment available for relaxation.

## Key Features

- **Immersive VR environments:** Traffic/accident, elevator/confined space, and a calming natural environment.
- **Gradual exposure:** Adjustable environmental intensity across four exposure levels.
- **Anxiety assessment:** User-reported anxiety ratings on a 0–10 scale before, during, and after sessions.
- **Adaptive exposure control:** Rule-based decisions to maintain, reduce, or pause exposure according to reported anxiety.
- **Guided support:** Context-aware calming prompts and breathing exercises.
- **Safety controls:** Session pause, reduced intensity, and access to the calming environment.
- **Session reports:** Clear summaries of duration, starting anxiety, peak anxiety, ending anxiety, and exposure level.
- **Progress tracking:** Session history and anxiety trends.
- **Clinician dashboard:** Access to permitted session records and review notes.

## Technology Stack

The intended architecture includes:

- Frontend: React and Vite
- 3D environments: Three.js, React Three Fiber, and Drei
- VR support: WebXR where supported
- Backend: Node.js and Express
- Database: The database configured for the project
- Visualization: Recharts or an equivalent charting library

The actual technologies and versions should be confirmed against the implementation.

## Project Structure

```text
MindSphere-VR/
├── frontend/
├── backend/
├── public/
│   └── assets/
├── docs/
│   ├── TECHNICAL_DESIGN.md
│   └── TEST_CASES.md
├── .env.example
├── .gitignore
├── README.md
└── LICENSE
```

The folders may differ depending on the final implementation.

## Prerequisites

Install the following before running the application:

- Node.js and npm
- Git
- Visual Studio Code or another code editor
- A modern browser supporting WebGL
- A compatible device and browser for WebXR, if VR mode is required

## Installation

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd MindSphere-VR
```

Install the frontend dependencies:

```bash
cd frontend
npm install
```

Install backend dependencies:

```bash
cd ../backend
npm install
```

Return to the project root when needed:

```bash
cd ..
```

These commands assume separate `frontend` and `backend` folders. Adjust them if the actual project uses a different structure.

## Environment Configuration

Create environment files based on `.env.example`.

Configure the required values for:

- Backend port
- Database connection
- Authentication secrets, if applicable
- Frontend API URL
- External service credentials, if required

Never commit real passwords, API keys, tokens, or database credentials.

## Running the Application

Start the backend in its directory:

```bash
npm run dev
```

Start the frontend in a separate terminal:

```bash
cd frontend
npm run dev
```

Use the local URL printed by Vite to open the website.

The actual commands must match the scripts defined in the project's `package.json` files.

## How It Works

1. The user signs in and provides consent.
2. The user records a pre-session anxiety rating.
3. The user selects an exposure scenario.
4. The application loads the selected 3D environment.
5. The exposure controller adjusts the environment according to reported anxiety.
6. The user can pause, request support, or enter the calming environment.
7. The application collects a post-session rating and generates a session report.
8. Session data is stored for progress tracking and authorized review.

## Important Safety Information

MindSphere-VR is a technology platform for guided immersive experiences and session tracking. It does not diagnose PTSD or other mental-health conditions and does not replace professional mental-health care. Anxiety ratings are user-reported and should not be interpreted as clinical measurements.

## Future Enhancements

- Integration with compatible physiological sensors
- Additional realistic VR assets and environments
- Enhanced clinician review workflows
- More comprehensive usability and safety testing
- Evaluation with qualified mental-health professionals

## License

The project license is specified in the `LICENSE` file.

