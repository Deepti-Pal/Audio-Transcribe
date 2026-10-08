Audio Transcribe

A Spring Boot application that uses Spring AI to convert speech in audio files into text.

Features
Upload an audio file and get its transcription as text
Built on Spring Boot and Spring AI
Simple REST API, easy to test with Postman or curl
Configurable AI model and API key through application.properties
Tech Stack
Java 17+
Spring Boot
Spring AI
Maven
Prerequisites
JDK 17 or later
Maven 3.8+ (or use the included Maven wrapper)
An API key for your AI provider (for example, OpenAI)
Getting Started
1. Clone the repository
bash
git clone https://github.com/Deepti-Pal/audio-transcribe.git
cd audio-transcribe
2. Configure your API key

Open src/main/resources/application.properties and add:

properties
spring.ai.openai.api-key=${OPENAI_API_KEY}

Then set the environment variable.

Windows (PowerShell):

powershell
$env:OPENAI_API_KEY="your-api-key"

Mac / Linux:

bash
export OPENAI_API_KEY="your-api-key"

Never commit your API key to GitHub.

3. Run the application
bash
./mvnw spring-boot:run

On Windows PowerShell:

powershell
.\mvnw.cmd spring-boot:run

The app starts at http://localhost:8080.

Usage

Send an audio file to the transcription endpoint:

bash
curl -X POST http://localhost:8080/transcribe \
  -F "file=@sample.mp3"

Example response:

json
{
  "text": "Hello, this is a sample transcription."
}

The endpoint path may differ depending on the controller in the code. Check the @RequestMapping / @PostMapping annotations in the controller class.

Project Structure
audio-transcribe/
├── src/
│   ├── main/
│   │   ├── java/          # Application source code
│   │   └── resources/     # Configuration files
│   └── test/              # Tests
├── pom.xml                # Maven dependencies
└── README.md
Supported Audio Formats

Common formats such as MP3, MP4, WAV, M4A, and WEBM (depends on the AI provider you use).




