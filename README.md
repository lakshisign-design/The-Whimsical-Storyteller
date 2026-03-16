# The Whimsical Storyteller

A magical visual storytelling app for children with voice interaction and dynamic stories.

## 🧪 Reproducible Testing Instructions

To help judges easily evaluate The Whimsical Storyteller, follow these steps to test the core multimodal storytelling and voice agent features locally.

### 1. Complete Environment Setup
Ensure your local environment or deployment contains the required API key for the core agent logic:
* `GEMINI_API_KEY`=your_api_key (Required for narrative logic and visual prompt generation)

### 2. Start the Application
Run `npm run dev` and open the provided `localhost` link in your browser. Ensure your speakers are on and your browser has microphone permissions granted.

### 3. Step-by-Step Test Scenarios

**Test Scenario 1: Initializing a Dynamic Story**
1.  On the main interface, locate the input area or use the microphone button.
2.  Provide a starting prompt, for example:
    > *"Start a new story about a brave space hamster exploring the galaxy."*
3.  **Expected Result:** The AI will generate the first story segment, render an accompanying whimsical illustration, and present exactly three distinct, interactive choices at the bottom of the screen.

**Test Scenario 2: Voice-Activated Branching (Live Agent)**
1.  With the first page loaded, click the "🎤 Voice Command" button.
2.  Read the choices on the screen and speak one of the implied "Magic Words" (e.g., if a choice is "Fly to the cheese moon," simply say *"Fly"* or *"Moon"*).
3.  **Expected Result:** The application will process your voice intent, trigger the visual page-turn animation, and dynamically generate the *next* segment of the story along with a brand-new generated image based strictly on your spoken choice.

**Test Scenario 3: The Storyteller Voice (Accessibility)**
1.  On any newly generated story page, click the "🔊 Read to Me" button.
2.  **Expected Result:** The app will read the current narrative segment aloud using an engaging, child-friendly voice pitch, demonstrating the multimodal Text-to-Speech output designed for younger, non-reading users.

## Deployment to Google Cloud Run

This project is configured to be deployed to Google Cloud Run via a Git repository.

### Prerequisites

1.  A Google Cloud Project.
2.  The Google Cloud SDK installed and configured.
3.  A Gemini API Key from [Google AI Studio](https://aistudio.google.com/).

### Environment Variables

You must set the following environment variable in your Cloud Run service:

-   `GEMINI_API_KEY`: Your API key for the Gemini AI.

### Local Development

1.  Install dependencies:
    ```bash
    npm install
    ```
2.  Start the development server:
    ```bash
    npm run dev
    ```

### Build and Run Locally with Docker

1.  Build the image:
    ```bash
    docker build -t whimsical-storyteller .
    ```
2.  Run the container:
    ```bash
    docker run -p 3000:3000 -e GEMINI_API_KEY=your_api_key whimsical-storyteller
    ```

### Deployment via Git

1.  Push this repository to your preferred Git provider (e.g., GitHub, GitLab).
2.  In the Google Cloud Console, go to **Cloud Run**.
3.  Click **Create Service**.
4.  Select **Continuously deploy from a repository**.
5.  Follow the prompts to connect your repository and select the branch.
6.  In the **Configuration** section, under **Container(s)**, add the `GEMINI_API_KEY` environment variable.
7.  Set the container port to `3000`.
8.  Click **Create**.
