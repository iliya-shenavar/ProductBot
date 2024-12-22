# Telegram Bot for Product Updates and Price Monitoring

This project is a **Telegram Bot** designed for managing product updates and price monitoring by integrating Excel data and Telegram channels. It automates posting and updating product information, ensuring efficiency and accuracy.

---

## Features

- **Excel Integration**: Automatically manages product data stored in Excel files.
- **Telegram Channel Updates**:
  - Posts product details (code, name, price, and image).
  - Edits existing posts when product prices change.
- **Data Persistence**:
  - Tracks posted products using JSON files.
  - Prevents duplicate postings by maintaining a record of uploaded posts.
- **Localized Date Support**: Uses Persian date formatting with `jdatetime`.
- **Asynchronous Operation**: Efficiently handles Telegram API calls using `asyncio`.
- **Error Handling**: Includes retry mechanisms for robust operation.

---

## Getting Started

### Prerequisites

- **Python 3.8+**
- Required libraries: `openpyxl`, `python-telegram-bot`, `jdatetime`

Install dependencies:
```bash
pip install openpyxl python-telegram-bot jdatetime
```

### Environment Setup

Set your Telegram Bot token as an environment variable:
```bash
export TELEGRAM_BOT_TOKEN="YOUR_BOT_TOKEN"
```

---

## File Structure

- **`products.xlsx`**: Stores product data (code, name, price, and image URL).
- **`message_ids.json`**: Tracks Telegram message IDs for posted products.
- **`uploaded_posts.txt`**: Keeps a record of already uploaded product codes.

---

## Usage

1. **Prepare the Excel File**:
   - Ensure the file `products.xlsx` exists with the following columns:
     - Product Code
     - Product Name
     - Price
     - Image URL
   - The bot will create the file automatically if it doesn't exist.

2. **Run the bot**:
   ```bash
   python bot.py
   ```

3. **Functionality**:
   - Automatically posts new products to the specified Telegram channel.
   - Updates existing posts when prices change.
   - Prevents duplicate postings by checking `uploaded_posts.txt`.

---

## Key Functions

### Posting Product Information

- Sends product details (code, name, price, and image) to the Telegram channel.
- Stores message IDs in `message_ids.json` for future updates.

### Price Monitoring and Updates

- Checks the Excel file for changes in product prices.
- Updates Telegram posts if prices are modified.

### Error Handling

- Retries operations in case of network or API errors.
- Logs errors for debugging and monitoring.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contact

For any inquiries or support, contact the project maintainer.

---

## Disclaimer

This bot stores user data locally. Ensure appropriate security measures when deploying the bot to protect user privacy.

