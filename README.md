# AI Health Assistant

## Project Description
The **AI Health Assistant** is a machine learning and natural language processing (NLP) powered application designed to provide virtual healthcare support. Built in a Google Colab environment, it leverages the IBM Granite language model and a Naive Bayes classifier to offer three core functionalities:

1. **Patient Chat Assistant**: A conversational AI that answers medical questions empathetically using the IBM Granite model.
2. **Disease Prediction**: Predicts potential diseases based on user-input symptoms using a Naive Bayes classifier trained on a symptom-disease dataset.
3. **Personalized Treatment Plan**: Generates general, safe treatment recommendations for a diagnosed disease using the language model.

The application is accessible through an interactive Gradio interface, making it user-friendly for non-technical users. This project is ideal for exploring AI-driven healthcare solutions, prototyping virtual health assistants, or educational purposes in medical AI.

## Features
- **Conversational AI**: Responds to medical queries with clear, empathetic answers.
- **Symptom-Based Diagnosis**: Predicts diseases from comma-separated symptom inputs.
- **Treatment Suggestions**: Provides general treatment plans for specified diseases.
- **Interactive UI**: Gradio-based web interface for easy interaction.
- **Cloud-Based**: Runs in Google Colab with GPU support for efficient model inference.

## Tools and Technologies
- **Google Colab**: Cloud-based Jupyter Notebook environment with GPU support.
- **Python**: Version 3.x, the primary programming language.
- **Machine Learning and NLP Libraries**:
  - `transformers`: For loading and using the IBM Granite model.
  - `datasets`: For handling datasets (if applicable).
  - `accelerate`: For optimized model inference.
  - `scikit-learn`: For the Naive Bayes classifier and text vectorization.
  - `pandas`: For data manipulation.
- **Gradio**: For creating the interactive web interface.
- **Hugging Face Hub**: For accessing the IBM Granite model (`ibm-granite/granite-3.3-2b-instruct`).
- **Dataset**: A custom `symptoms_disease_dataset.csv` file for disease prediction (must be provided by the user).
- **Google Drive**: For storing datasets and outputs (optional).

## Prerequisites
- A Google account to access Google Colab.
- A Hugging Face account and API token for model access (e.g., `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`).
- The `symptoms_disease_dataset.csv` file uploaded to Colab or Google Drive.
- Basic knowledge of Python, machine learning, and NLP.
- Internet connection for running the Colab notebook and accessing Hugging Face models.

## Setup Instructions
1. **Access the Notebook**:
   - Open the Google Colab notebook: [Insert the Colab link here or note it’s included in the repository].
   - Alternatively, download `ai_health_assistant.ipynb` from this repository and upload it to [Google Colab](https://colab.research.google.com/).

2. **Install Dependencies**:
   - Run the first cell to install required libraries:
     ```bash
     !pip install transformers datasets accelerate gradio pandas scikit-learn
     ```
   - Ensure all dependencies are installed before proceeding.

3. **Authenticate with Hugging Face**:
   - Replace the placeholder token in the `login()` function with your Hugging Face API token:
     ```python
     from huggingface_hub import login
     login("your_hugging_face_token")
     ```

4. **Upload Dataset**:
   - Upload the `symptoms_disease_dataset.csv` file to your Colab environment or Google Drive.
   - If using Google Drive, mount it in Colab:
     ```python
     from google.colab import drive
     drive.mount('/content/drive')
     ```

5. **Configure Hardware**:
   - For faster inference, enable GPU: Go to `Runtime > Change runtime type` and select `GPU`.

## Usage
1. **Open the Notebook**:
   - Load the notebook in Google Colab and execute cells sequentially (`Shift + Enter`).

2. **Run the Gradio Interface**:
   - Execute the final cell to launch the Gradio app:
     ```python
     demo.launch()
     ```
   - A public URL will be generated for accessing the interface.

3. **Interact with the Assistant**:
   - **Patient Chat Assistant**: Enter a medical question (e.g., "What are the symptoms of flu?") and receive a response.
   - **Disease Prediction**: Input symptoms (e.g., "fever, cough, fatigue") to predict a disease.
   - **Personalized Treatment Plan**: Enter a diagnosed disease (e.g., "influenza") to get a general treatment plan.

4. **Save Outputs**:
   - Save model outputs or Gradio screenshots to Google Drive or download them via Colab’s file menu.

## Project Structure
- `ai_health_assistant.ipynb`: The main Colab notebook containing the project code.
- `README.md`: This file, providing an overview and instructions.
- `symptoms_disease_dataset.csv`: Required dataset for disease prediction (not included; user must provide).
- (Optional) `outputs/`: Directory for saving model outputs or visualizations.

## Example
```python
# Example: Predicting a disease
symptoms = "fever, cough, sore throat"
predicted_disease = predict_disease(symptoms)
print(f"Predicted Disease: {predicted_disease}")

# Example: Generating a treatment plan
plan = treatment_plan("influenza")
print(plan)
```

## Notes
- **Dataset**: The `symptoms_disease_dataset.csv` file must have columns `Symptoms` and `Disease`. Ensure it’s uploaded to Colab or Google Drive.
- **Model Access**: The IBM Granite model requires a Hugging Face token. Replace the token in the code with your own.
- **Gradio**: The public URL generated by Gradio is temporary. For persistent access, consider deploying the app elsewhere.
- **Safety**: The treatment plans are general and not a substitute for professional medical advice.

## Contributing
Contributions are welcome! To contribute:
1. Fork this repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make changes to the notebook or add new features.
4. Commit your changes (`git commit -m "Add new feature"`).
5. Push to the branch (`git push origin feature-branch`).
6. Open a pull request.


## Acknowledgments
- **Hugging Face** for providing the IBM Granite model and `transformers` library.
- **Gradio** for the user-friendly interface.
- **scikit-learn** for the Naive Bayes classifier.
- **Google Colab** for the free cloud-based environment.
