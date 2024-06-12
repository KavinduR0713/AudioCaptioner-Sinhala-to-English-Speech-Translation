# AudioCaptioner-Sinhala-to-English-Speech-Translation
AudioCaptioner is a robust Python-based application that leverages advanced data science techniques for speech recognition and translation. This project focuses on converting Sinhala audio files into English text captions, making it an invaluable tool for accessibility, content creation, and language learning. By integrating SpeechRecognition and Google Translate APIs, AudioCaptioner transforms spoken Sinhala language into written English, demonstrating the power of natural language processing and machine learning in real-world applications.

## Key Features

### 1. Speech Recognition
- Utilizes the speech_recognition library to process audio files and convert speech into text.
- Configured to recognize Sinhala (si-LK) language, ensuring accurate transcription of Sinhala audio input.

### 2. Language Translation
- Integrates googletrans library for translating the transcribed Sinhala text into English.
- Provides seamless and accurate translation, making the content accessible to a broader audience.

### 3. Error Handling
- Includes robust error handling to manage scenarios where the audio is not understood or the Google Speech Recognition service is unavailable.
- Returns meaningful error messages to guide the user in troubleshooting issues.

### 4. Detailed Documentation
- Offers comprehensive documentation covering installation, usage, and the underlying data science techniques employed in the project.
- Provides examples and use cases to help users understand and utilize the tool effectively.

## How It Works

### Speech Recognition
The core of AudioCaptioner’s speech recognition capability is powered by the speech_recognition library. This library interfaces with the Google Web Speech API to convert audio data into text. The following steps outline the process:

   #### 1. Loading the Audio File:

   - The audio file is loaded using sr.AudioFile, which allows the application to read the file and prepare it for processing.
   - The audio data is captured using recognizer.record(source), ensuring the entire audio file is processed.

   #### 2. Recognizing Speech:

   - The recognizer.recognize_google function is invoked with show_all=True and language="si-LK" parameters.
   - This function call specifies the use of Sinhala language for speech recognition and requests all possible transcriptions.
   - The result is a dictionary containing multiple transcription alternatives.

   #### 3. Extracting and Validating Transcription:

   - The code checks for the presence of alternatives and selects the first one as the most likely transcription.
   - A validation step ensures the transcription is final before proceeding.

### Language Translation
Once the speech is recognized and transcribed, AudioCaptioner translates the text from Sinhala to English using the googletrans library:

   #### 1. Initializing the Translator:

   - A Translator object is created to facilitate the translation process.
   - The transcribed Sinhala text is passed to the translate function with src="si" and dest="en" parameters, indicating the source and target languages.

   #### 2. Performing the Translation:

   - The translator.translate function processes the text and returns the translated English version.
   - This translated text is then returned as the final output of the application.

### Error Handling
AudioCaptioner includes comprehensive error handling to manage various potential issues:

   #### 1. UnknownValueError:

   - This error is caught when the speech recognition service cannot understand the audio input.
   - An appropriate message is returned to inform the user about the issue.

   #### 2. RequestError:

   - This error occurs when there is a problem with the Google Web Speech API request.
   - The error message includes details to help the user diagnose and fix the problem.
