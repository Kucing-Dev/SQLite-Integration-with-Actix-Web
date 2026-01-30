# SQLite Integration with Actix Web (Rust)

This project is a simple example of **integrating SQLite with Actix Web using Rust**. It provides a basic REST API to manage *posts* (blog posts) using **SQLx** as the asynchronous database layer.

---

## 🚀 Features

* Actix Web as the web framework
* SQLite as a lightweight, file-based database
* SQLx for asynchronous database access
* REST API endpoints:

  * `GET /posts` → retrieve all posts
  * `POST /posts` → create a new post
* Simple and clean project structure (suitable for learning or academic assignments)

---

## 🛠️ Tech Stack

* **Rust**
* **Actix Web 4**
* **SQLx (SQLite)**
* **Serde** (JSON serialization/deserialization)

---

## 📂 Project Structure

```text
SQLiteIntegration_actix/
├── Cargo.toml
├── Cargo.lock
├── blog.db           # SQLite database file
├── posts.sql         # SQL schema
├── src/
│   └── main.rs       # Application entry point
└── target/
```

---

## 🧱 Database Schema

File: `posts.sql`

```sql
CREATE TABLE IF NOT EXISTS posts (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    content TEXT NOT NULL
);
```

### Create the database manually

```bash
sqlite3 blog.db < posts.sql
```

---

## 📦 Main Dependencies

```toml
[dependencies]
actix-web = "4"
serde = { version = "1", features = ["derive"] }
sqlx = { version = "0.7", features = ["sqlite", "runtime-tokio-native-tls"] }
tokio = { version = "1", features = ["macros", "rt-multi-thread"] }
```

---

## ▶️ Running the Application

```bash
cargo run
```

The server will start at:

```
http://127.0.0.1:8080
```

---

## 🔗 API Endpoints

### 1️⃣ Get all posts

```http
GET /posts
```

Example response:

```json
[
  {
    "id": 1,
    "title": "SQLite Test",
    "content": "Rust + SQLx is cool"
  }
]
```

---

### 2️⃣ Create a new post

```http
POST /posts
Content-Type: application/json
```

Request body:

```json
{
  "title": "SQLite Test",
  "content": "Rust + SQLx is cool"
}
```

Test using `curl`:

```bash
curl -X POST http://127.0.0.1:8080/posts \
  -H "Content-Type: application/json" \
  -d '{"title":"SQLite Test","content":"Rust + SQLx is cool"}'
```

---

## 📸 Screenshot

<img width="1365" height="681" alt="Screenshot 2026-01-29 114535" src="https://github.com/user-attachments/assets/a6806780-b5ae-4c3d-941f-7bd9a0a55b60" />


* Data successfully inserted into SQLite
* The `/posts` endpoint returns JSON data correctly

---

## 🎓 Learning Notes

This project is suitable for:

* Learning Rust backend development
* Understanding Actix Web + SQLite integration
* Academic assignments or backend practicums
* Building a basic REST API with Rust

---

## 📌 Future Improvements (Optional)

* [ ] GET `/posts/{id}`
* [ ] DELETE `/posts/{id}`
* [ ] Update post endpoint
* [ ] SQLx migrations
* [ ] Improved error handling

---

## 👤 Author

**Khairunnisya Lubis**
Rust & Backend Learner. 🚀

---

⭐ If you find this project helpful, feel free to give it a star on GitHub!
