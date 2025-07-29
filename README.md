# 🚀 Anomaly description from a rover using VLM

This project automates the process of identifying visual anomalies from Mars-like terrain images using a Vision-Language Model (VLM) and generates a clean PDF report using FPDF.

## 📌 Overview

- Input images (e.g., from a rover camera) are passed to the **Qwen 2.5 VL** model via OpenRouter API.
- The model provides structured anomaly descriptions.
- These descriptions, along with images, are compiled into a formatted PDF using `fpdf`.

## 🧠 Why Qwen 2.5 VL?

- 8k token limit allows for detailed prompt + image input.
- Generates structured, concise outputs suitable for documentation.
- Easily accessible via API (OpenRouter).

## 🛠️ Workflow

```
📁 Anomaly_Images Folder
        ⬇
Qwen 2.5 VL (via API + custom prompt)
        ⬇
📝 FPDF-based Report Generator
        ⬇
📄 anomaly_report.pdf
```

## ⚙️ Setup

1. Clone the repo and install dependencies

2. Set your `api_key`  in your script or `.env`.

3. Place input `.jpeg` images inside the `Ground_images/` folder (named using `lat_long.jpeg` format).

4. Customize your prompt in `prompt.txt` (loaded dynamically by the code).

## 🧪 Indoor Testing Mode

- For indoor test runs (specially designed for payload challenge), the model prompt is modified to suit **Earth-based indoor environments**.
- This ensures the model doesn’t hallucinate Mars-like context in indoor tests.

## 📂 Output

- A clean, aligned `anomaly_report.pdf` is generated summarizing all detected anomalies with image and structured metadata.

## 📋 Logs

- Detailed logs (`INFO` level) are generated for monitoring each image analysis, including retries and error handling.
