# The Whimsical Storyteller

A magical visual storytelling app for children with voice interaction and dynamic stories.

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
