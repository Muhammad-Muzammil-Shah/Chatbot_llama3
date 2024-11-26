# Groq Chat Completion Example

This repository demonstrates how to use the **Groq API** to create a simple chat application with Python. The script takes user input, sends it to the Groq API, and prints the model's response.

---

## **Getting Started**

Follow these steps to set up and run the script:

---

### **Step 1: Create an API Key**
1. Visit the [Groq API Key Page](#) to generate your API key.

---

### **Step 2: Set Up Your Environment**
It’s recommended to set your API key as an environment variable to enhance security.

#### **In your terminal:**
```bash
import os
os.environ["GROQ_API_KEY"] = ""
```

---

### **Step 3: Install Dependencies**
Install the required Groq Python library:
```bash
pip install groq
```

---

### **Step 4: Run the Script**

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/groq-chat-example.git
   cd groq-chat-example
   ```
2. Run the Python script:
   ```bash
   python app.py
   ```

---

## **Code Overview**
Here’s what the script does:

### **Python Code:**
```python
import os
os.environ["GROQ_API_KEY"] = "GROQ_API_KEY"
from groq import Groq

# Initialize the Groq client with the API key
client = Groq(
    api_key=os.environ.get("GROQ_API_KEY"),
)

# Prompt user input and send a message to the Groq API
chat_completion = client.chat.completions.create(
    messages=[
        {
            "role": "user",
            "content": input("Chat with me Dear: "),
        }
    ],
    model="llama3-8b-8192",  # Specify the model
)

# Print the response from the model
print(chat_completion.choices[0].message.content)
```

### **How It Works:**
1. **API Key**: The script fetches the API key from the environment variable `GROQ_API_KEY`.
2. **User Input**: Prompts the user with `Chat with me Dear: ` and captures the input.
3. **Groq API Call**: Sends the input to the `llama3-8b-8192` model.
4. **Prints Response**: Displays the model’s response in the terminal.

---

## **Next Steps**
- Experiment with other models or endpoints in the [Groq API Documentation](#).
- Check out the **Playground** to test Groq API directly in your browser.
- Join the [GroqCloud Developer Discord Community](#) to connect with other developers.

---

## **Contributing**
Feel free to open issues or submit pull requests to enhance the repository.

---

## **License**
This project is open-source and available under the [MIT License](LICENSE).
