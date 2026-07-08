# 📚 Library Management System

A simple, clean library management app built with **Python**, **Streamlit**, and **PostgreSQL (Supabase)** — store books, issue them to readers, and track availability, all from a browser-based dashboard.

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-App-red?logo=streamlit)
![PostgreSQL](https://img.shields.io/badge/Database-Supabase%20Postgres-3ecf8e?logo=supabase)

---

## ✨ Features

- **Add books** to the library with a single form
- **Issue books** to borrowers with automatic fine calculation (₹10/day after 7 days)
- **Live dashboard** showing total, available, and issued book counts
- **Status badges** for quick visual tracking (Available / Issued)
- Persistent storage using a hosted **PostgreSQL** database (Supabase)

---

## 🖥️ Tech Stack

| Layer      | Technology              |
|------------|--------------------------|
| Frontend   | Streamlit                |
| Backend    | Python 3.11               |
| Database   | PostgreSQL (Supabase)    |
| DB Driver  | psycopg2                 |
| Config     | python-dotenv             |

---

## 📂 Project Structure

```
library/
├── app.py           # Streamlit dashboard (UI)
├── sql.py           # Database class (all DB operations)
├── .env              # Environment variables (not committed)
├── requirements.txt   # Python dependencies
└── README.md
```

---

## ⚙️ Setup & Installation

### 1. Clone the repository
```bash
git clone https://github.com/darshanbedi321-code/<repo-name>.git
cd library
```

### 2. Create a virtual environment
```bash
conda create -n ml_env python=3.11
conda activate ml_env
```

### 3. Install dependencies
```bash
pip install streamlit psycopg2-binary python-dotenv
```

### 4. Configure environment variables
Create a `.env` file in the project root:
```env
DB_HOST=your-supabase-pooler-host
DB_PORT=6543
DB_NAME=postgres
DB_USER=postgres.your-project-ref
DB_PASSWORD=your-database-password
```

> ⚠️ Never commit your `.env` file. Add it to `.gitignore`.

### 5. Create the database table
Run this in your Supabase SQL Editor:
```sql
CREATE TABLE darshan (
    id SERIAL PRIMARY KEY,
    bookname VARCHAR(255) NOT NULL,
    status VARCHAR(50) DEFAULT 'available',
    issuedby VARCHAR(255),
    days INT,
    fined INT
);
```

### 6. Run the app
```bash
streamlit run app.py
```

---

## 🚀 Usage

1. **Add Book** — Enter a book title and store it in the library.
2. **Issue Book** — Select an available book, enter the borrower's name and number of days. Fine is calculated automatically for durations over 7 days.
3. **Available Books** — View all books currently available for issue.
4. **All Books** — View the complete inventory with status.

---

## 🔐 Security Notes

- Database credentials are managed via `.env` using `python-dotenv` and are never hardcoded.
- If a credential is ever exposed, reset it immediately from the Supabase dashboard.

---

## 🗺️ Roadmap / Future Improvements

- [ ] Book return functionality with fine settlement
- [ ] Search & filter books by name/status
- [ ] User authentication for librarian access
- [ ] Book categories/genres
- [ ] Deployment on Streamlit Cloud

---

## 👤 Author

**Darshan Bedi**
B.Tech CSE, ICFAI University, Himachal Pradesh
GitHub: [darshanbedi321-code](https://github.com/darshanbedi321-code)

---

## 📄 License

This project is open source and available for learning purposes.
