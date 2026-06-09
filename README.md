# AI Code Explainer using Streamlit and Gemini API

## Overview

AI Code Explainer is a web application built using Python, Streamlit, and Google's Gemini AI model.
The application helps users understand programming code by providing detailed explanations and expected outputs.

Users can enter any programming code or coding-related question, and the AI explains:

* Code functionality
* Logic flow
* Expected output

If the input is unrelated to coding, the application responds with:
`Invalid Question`

---

## Features

* Explain programming code
* Describe code execution flow
* Predict and explain output
* Supports coding-related questions
* Invalid question detection
* Simple and interactive UI

---

## Technologies Used

* Python
* Streamlit
* Google Generative AI (Gemini API)

---

## Project Structure

```bash id="rf44fu"
AI-Code-Explainer/
│
├── app.py
├── requirements.txt
└── README.md
```

---

## Installation

### 1. Clone the Repository

```bash id="kznjpa"
git clone https://github.com/your-username/AI-Code-Explainer.git
```

### 2. Navigate to the Project Folder

```bash id="7l6ftw"
cd AI-Code-Explainer
```

### 3. Install Required Packages

```bash id="jlwm4m"
pip install -r requirements.txt
```

---

## Required Packages

Create a `requirements.txt` file and add:

```txt id="q3n5u8"
streamlit
google-generativeai
```

---

## API Key Setup

Get your Gemini API key from Google AI Studio:

https://aistudio.google.com/

Replace:

```python id="0qt8fd"
gen.configure(api_key = "YOUR API KEY")
```

with your actual API key.

Example:

```python id="crj8zn"
gen.configure(api_key="AIzaSyXXXXXX")
```

---

## Application Code

```python id="ujmjlwm"
import streamlit as st
import google.generativeai as gen

gen.configure(api_key = "YOUR API KEY")

model = gen.GenerativeModel("gemini-2.5-flash")

prompt = st.text_input("Answer any questions asked by the user")

if st.button("Submit"):
    res = model.generate_content(
        prompt + " you are a code explainer, explain the code and also explain the output of the coding. other than that you say invalid question."
    )
    
    st.write(res.text)
```

---

## Run the Application

Use the following command:

```bash id="m2m63p"
streamlit run app.py
```

---

## Example Use Cases

* Java code explanation
* Python code explanation
* C/C++ logic understanding
* Output prediction
* Beginner coding learning
* Debugging assistance

---

## Sample Input

```python id="0e86a3"
for i in range(5):
    print(i)
```

---

## Sample Output

```txt id="0r5nzs"
This loop runs from 0 to 4 using the range() function.

Output:
0
1
2
3
4
```

---

## Future Enhancements

* Multi-language code support
* Syntax highlighting
* Code execution support
* Voice explanation
* Dark mode UI
* Copy explanation feature

---

## Author

Arun

---

## License

This project is for educational purposes only.
