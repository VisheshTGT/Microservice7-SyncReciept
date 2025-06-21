# 🧾 Business Sync Service

A backend service to capture and sync receipts to client CRM/ERP platforms like **Zoho**, **Tally**, and **QuickBooks**.

---

## 🚀 Features

- Capture receipts and metadata
- Sync with:
  - ✅ Zoho Books
  - ✅ QuickBooks Online
  - ✅ Tally ERP
- View and manage receipt sync status
- Modular and extensible architecture

---

## 🛠 Tech Stack

- Node.js
- Express.js
- MongoDB + Mongoose
- REST APIs
- OAuth2 (Zoho, QuickBooks)
- XML via HTTP (Tally)

---

## 📁 Project Structure

```
project/
├── app.js
├── .env
├── routes/
│   └── receipt.routes.js
├── controllers/
│   └── receipt.controller.js
├── services/
│   ├── syncQuickBooks.js
│   ├── syncZoho.js
│   └── syncTally.js
├── models/
│   └── receipt.model.js
├── middleware/
│   └── errorHandler.js
├── utils/
│   └── mapper.js
```

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/business-sync-service.git
cd business-sync-service
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment

Create a `.env` file:

```
MONGO_URI=mongodb://localhost:27017/business_sync_db
```

### 4. Start the Server

```bash
npm start
```

Server will run on `http://localhost:3000`.

---

## 📡 API Endpoints

### ➕ Create Receipt

```
POST /api/receipts
```

**Request Body:**

```json
{
  "vendor": "Amazon",
  "date": "2025-06-19",
  "amount": 1599,
  "tags": ["office"],
  "platform": "quickbooks"
}
```

### 🔄 Sync Receipt

```
POST /api/receipts/:id/sync
```

Syncs the selected receipt to the specified platform.

### 🔍 Get Receipt

```
GET /api/receipts/:id
```

Returns the receipt details including sync status.

---

## 🧩 Example Receipt Object

```json
{
  "_id": "664d2487c7a9fa7f7c123456",
  "vendor": "Amazon",
  "amount": 2500,
  "date": "2025-06-19T00:00:00.000Z",
  "tags": ["electronics"],
  "platform": "zoho",
  "status": "pending",
  "metadata": {
    "invoice_no": "AMZ123",
    "payment_method": "credit card"
  }
}
```

---

## 📌 To-Do / Roadmap

- [ ] Add authentication (JWT)
- [ ] Add webhook support
- [ ] Background sync using BullMQ
- [ ] Sync logs UI (React dashboard)

---

## 🤝 Contributing

1. Fork the repo
2. Create your feature branch: `git checkout -b feature/new-feature`
3. Commit your changes: `git commit -m 'Add new feature'`
4. Push to the branch: `git push origin feature/new-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 📬 Contact

For questions, issues, or suggestions:
- 📧 Email: `vishesh.9612@gmail.com`
- 📂 GitHub Issues: [Submit here](https://github.com/vishu-cpp/business-sync-service/issues)

