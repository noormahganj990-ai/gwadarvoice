GwadarVoice - Civic Complaint Classifier

GwadarVoice classifies citizen complaints written in Roman Urdu, English, or a mix of both into 6 categories: Water, Electricity, Roads, Garbage, Healthcare and Security, and suggests the department that should handle them.

Links
Pretrained model: https://huggingface.co/xlm-roberta-base
Fine-tuned model: https://huggingface.co/YOUR_HF_USERNAME/gwadarvoice-xlmr-complaints
Live app: (add your Streamlit link here)
Problem statement

Complaints in coastal towns like Gwadar are often written in code-mixed Roman Urdu ("bijli nahi hai since yesterday"). Sorting them by hand is slow. This project automates it.

Dataset

A new, custom dataset created by the author:

Template-generated code-mixed complaints using Gwadar locations (Sur Bandar, Pishukan, Jiwani, Marine Drive...)
Hand-written real-style complaints added by the author
Test sets use held-out issue phrases and a hand-written set to avoid over-optimistic scores

Files are in the data/ folder (train, validation, test).

Model

xlm-roberta-base fine-tuned for 4 epochs (learning rate 2e-5, batch size 16) with a 6-class classification head (transfer learning).

Run locally
pip install -r requirements.txt
streamlit run app.py
Project pipeline
Dataset creation, cleaning and splitting
Fine-tuning xlm-roberta-base on Google Colab
Uploading the model to Hugging Face
Code hosted on GitHub
Streamlit app deployed on Streamlit Community Cloud
Limitations

Most training data is generated from templates, so accuracy on very different real-world complaints may be lower. Future work: collect more real complaints, support Urdu script and Balochi.
