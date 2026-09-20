# Excel Query Assistant

**Excel Query Assistant** is a web application built with **Streamlit** **Python** **SQLite**. The **Google Gemini API**.

The Excel Query Assistant lets users upload Excel (files. The Excel Query Assistant automatically turns those files into a database so you can ask questions about the data using plain language. Gemini then creates the SQL queries and the Excel Query Assistant shows the results in a Streamlit interface.

## Features

* **Excel File Upload** – Upload.xlsx files directly through the Excel Query Assistant.

* **Automatic Data Conversion** – The Excel Query Assistant turns Excel data into a SQLite database for querying.

* **Natural Language Queries** – Ask questions about your Excel data in language.

* **SQL Query Generation** – Gemini automatically creates SQL queries from the Excel Query Assistant’s questions.

* **Query Results** – View the retrieved information directly in the Excel Query Assistant’s Streamlit interface.

* **Simple Streamlit Interface** – An easy‑to‑use web interface for working with Excel data.

## Technologies Used

* **Python**

* **Streamlit**

* **SQLite**

* **Pandas**

* **Google Gemini API**

* **Google Generative AI Python SDK**

## Project Structure

```text

Excel-Query-Assisstant/

│

├── new.py

├── requirements.txt

├── README.md

└─ LICENSE

```

## Prerequisites

Before running the project make sure you have:

* Python installed

* Git installed

* A Google account

* A Google Gemini API key

* Internet connection

## Installation

### 1. Clone the Repository

Clone the repository using Git:

```bash

git clone https://github.com/Margamharini/Excel-Query-Assisstant.git

```

Move into the project directory:

```bash

cd Excel-Query-Assisstant

```

### 2. Install Required Packages

Install all required Python packages using `requirements.txt`:

```bash

pip install -r requirements.txt

```

If you are using Anaconda you can use:

```bash

python -m pip install -r requirements.txt

```

## Google Gemini API Key Setup

The Excel Query Assistant requires a Google Gemini API key to generate SQL queries.

### 1. Create an API Key

Create a Gemini API key through **Google AI Studio**.

Do not share your API key publicly. Commit it to GitHub.

### 2. Set the API Key

The Excel Query Assistant reads the API key using the following code:

```python

genai.configure(api_key=os.getenv("GOOGLE_API_KEY"))

```

Therefore you need to set the `GOOGLE_API_KEY` environment variable before running the Excel Query Assistant.

### Windows PowerShell

Open PowerShell in the project directory. Run:

```powershell

$env:GOOGLE_API_KEY="YOUR_API_KEY"

```

Replace `YOUR_API_KEY` with your actual Gemini API key.

**Example:**

```powershell

$env:GOOGLE_API_KEY="your-api-key-

```

Do not commit or upload the actual API key to GitHub.

## Running the Application

After installing the dependencies and setting the API key run the Streamlit application:

```bash

streamlit run new.py

```

If you are using Anaconda and want to make sure Streamlit runs with the Python environment use:

```powershell

C:\Users\YourUsername\anaconda3\python.exe -m streamlit run new.py

```

After starting the Excel Query Assistant Streamlit will display a local URL similar to:

```text

Local URL: http://localhost:8501

```

Open this URL in your web browser.

## How It Works

The Excel Query Assistant follows these steps:

1. **Upload an Excel File**

Upload an `file, through the Streamlit interface.

2. **Read the Excel Data**

The application reads the Excel file using Python and Pandas.

3. **Convert Data to SQLite**

The Excel data is converted into tables in a SQLite database.

4. **Ask a Question**

Enter a question about the data using natural language.

For example:

```text

What is the total sales amount?

```

5. **Generate SQL Query**

The Gemini API analyzes the question. Generates an SQL query that can be used to retrieve the required information.

6. **Execute the Query**

The generated SQL query is executed against the SQLite database.

7. **Display the Result**

The application displays the query result in the Streamlit interface.

## Example

Suppose you upload an Excel file containing:

| Name  | Department | Salary |

| ----- | ---------- | ------ |

Ravi  | IT         | 50000  |

| Priya | HR         | 45000  |

Arun  | IT         | 60000  |

You could ask:

```text

What is the salary of employees in the IT department?

```

The application can generate an SQL query similar to:

```sql

SELECT AVG(Salary)

FROM employees

WHERE Department = 'IT';

```

The result is then displayed in the application.

## Troubleshooting

### 1. `ModuleNotFoundError`

If you see an error such as:

```text

ModuleNotFoundError: No module named 'google.generativeai'

```

install the Google Generative AI package:

```bash

pip install google-generativeai

```

### 2. `DefaultCredentialsError`

If you see:

```text

DefaultCredentialsError: No API_KEY or ADC found

```

make sure that the `GOOGLE_API_KEY` environment variable has been set.

For PowerShell:

```powershell

$env:GOOGLE_API_KEY="YOUR_API_KEY"

```

Then restart the Streamlit application.

### 3. Gemini Model Not Found

If you see an error such as:

```text

404 models/gemini-pro is not found

```

the project may be using a Gemini model name.

Check the model configured in `new.py` and use a supported Gemini model according to the Google Gemini API documentation.

## Security

**Never upload your API key to GitHub.**

Do not write your API key directly into `new.py` for example:

```python

genai.configure(api_key="YOUR_SECRET_API_KEY")

```

Instead use the `GOOGLE_API_KEY` environment variable:

```python

genai.configure(api_key=os.getenv("GOOGLE_API_KEY"))

```

If you accidentally expose an API key publicly revoke it. Create a new one.

## Usage

1. Start the application.

2. Open the Streamlit URL in your browser.

3. Upload an Excel (`.xlsx`) file.

4. Wait for the file to be processed.

5. Enter a question, about the data.

6. Let the application generate the SQL query.

7. View the query results.

## License

This project is licensed under the [MIT License](LICENSE).