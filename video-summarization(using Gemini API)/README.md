# Video Summarization Project

This project demonstrates the process of extracting audio from a YouTube video, transcribing the audio to text, and summarizing the text using various AI models. The project showcases the use of `pytube` for downloading videos, `ffmpeg` for audio extraction, Hugging Face's `transformers` for speech recognition, and Google's Gemini model for text summarization and analysis.

## Project Description

The project is divided into several steps:
1. **Download YouTube Video**: Use `pytube` to download the audio stream of a YouTube video.
2. **Extract Audio from Video**: Use `ffmpeg` to extract the audio from the downloaded video file.
3. **Transcribe Audio to Text**: Use Hugging Face's `whisper` model to convert the audio into text.
4. **Summarize the Transcription**: Use Google's Gemini model to generate an abstract, key points, action items, and sentiment analysis from the transcription.

## Usage Instructions

To run this notebook, follow these steps:

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/yourusername/your-repo-name.git
    cd your-repo-name
    ```

2. **Install Dependencies**:
    Ensure you have Python and pip installed, then install the required packages:
    ```bash
    pip install pytube ffmpeg-python pydub transformers accelerate
    ```

3. **Run the Notebook**:
    Open the notebook in Jupyter or Google Colab and execute the cells step by step.

4. **API Key Configuration**:
    Ensure you have your Google API key set up in the environment. In Google Colab, you can set it like this:
    ```python
    from google.colab import userdata
    GOOGLE_API_KEY = userdata.get("GOOGLE_API_KEY")
    ```

## Example Outputs

Here are example outputs for each step:

1. **Downloading YouTube Video**:
    ```python
    youtube_url = 'https://www.youtube.com/watch?v=ySus5ZS0b94&t=195s'
    download_path = 'videos'
    video_path = download_youtube_video(youtube_url, download_path)
    ```

2. **Extracting Audio from Video**:
    ```python
    audio_path = video_path.replace(".mp4", ".mp3")
    extract_audio_from_video(video_path, audio_path)
    ```

3. **Transcribing Audio to Text**:
    ```python
    transcription = ''.join(result)
    print(transcription)
    ```

4. **Summarizing the Transcription**:
    ```python
    abstract = abstract_summary_extraction(transcription)
    key_points = key_points_extraction(transcription)
    action_items = action_item_extraction(transcription)
    sentiment = sentiment_analysis(transcription)
    ```

## Dependencies

The following libraries are used in this project:
- `pytube`: `>=12.1.0`
- `ffmpeg-python`: `>=0.2.0`
- `pydub`: `>=0.24.1`
- `transformers`: `>=4.10.0`
- `accelerate`: `>=0.5.1`
- `google-generativeai`: For using Google's Gemini model.

