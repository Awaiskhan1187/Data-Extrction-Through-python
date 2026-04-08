# Data-Extrction-Through-python
This project fetches top news headlines using the NewsAPI and processes the data into structured formats like JSON and CSV.
# 📰 NewsAPI Data Extraction Project (Python)

This project fetches top news headlines using the NewsAPI and processes the data into structured formats like JSON and CSV.

---

## 🚀 Features

* Fetch top headlines using NewsAPI
* Extract useful fields from raw JSON
* Store data in:

  * JSON file (`news.json`)
  * CSV file (`news.csv`)
* Basic error handling for API requests

---

## 🛠️ Technologies Used

* Python
* requests
* json
* csv

---

## 📂 Project Workflow

1. Send a request to NewsAPI
2. Receive raw JSON response
3. Extract important fields:

   * Title
   * Source
   * Author
   * Published Date
   * URL
4. Save data into JSON and CSV files

---

## 🔑 Setup Instructions

### 1. Install Dependencies

```bash
pip install requests
```

---

### 2. Get API Key

* Go to https://newsapi.org/
* Sign up and generate your API key

---

### 3. Add API Key

Replace this line in your code:

```python
API_KEY = "YOUR_API_KEY"
```

---

## 📌 Code Overview

### API Request

```python
response = requests.get(
    url + f"?country={country}&apiKey={API_KEY}"
)
```

---

### Data Extraction

```python
for article in raw_data['articles']:
    extracted_data['Title'].append(article.get('title'))
    extracted_data['Source'].append(article.get('source'))
    extracted_data['Author'].append(article.get('author'))
    extracted_data['Published Date'].append(article.get('publishedAt'))
    extracted_data['URL'].append(article.get('url'))
```

---

### Save to JSON

```python
with open("news.json", "a") as file:
    json.dump(extracted_data, file, indent=4)
```

---

### Save to CSV

```python
with open('news.csv', "a") as file:
    writer = csv.DictWriter(file, fieldnames=extracted_data.keys())
    writer.writerow(extracted_data)
```

---

## ⚠️ Known Issues / Improvements

* API key should not be hardcoded (use `.env` file)
* CSV writing should include headers (`writeheader()`)
* Appending (`"a"`) may duplicate data
* Better error handling can be added

---

## 📈 Future Improvements

* Add user input for country or topic
* Convert into CLI tool
* Build a web app using Flask
* Schedule automatic data fetching

---

## 🤝 Contributing

Feel free to fork and improve this project.

---

## 👨‍💻 Author

Awais Khan
GitHub: https://github.com/your-username
