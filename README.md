# 📚 BookBridge
 
A peer-to-peer textbook exchange platform that connects students to buy, sell, and swap used textbooks — cutting costs and reducing waste.
 
🔗 **Live Demo:** [book-bridge-teal.vercel.app](https://book-bridge-teal.vercel.app/)
📦 **Repository:** [github.com/adarsh23222/BookBridge](https://github.com/adarsh23222/BookBridge)
 
---
 
## 📸 Screenshots
 
<!-- Add screenshots here -->
| Home Page | Book Listing | Chat/WebSocket |
|---|---|---|
| ![Home](./screenshots/home.png) | ![Listing](./screenshots/listing.png) | ![Chat](./screenshots/chat.png) |
 
---
 
## ✨ Features
 
- 🔐 **User Authentication** — Secure signup/login using JWT-based auth
- 📖 **Book Listings** — Users can register books they want to sell with title, price, and condition
- 🔍 **Browse & Search** — Explore available textbooks from other students
- 💬 **Real-time Chat** — WebSocket-powered messaging between buyers and sellers
- ✅ **Sell/Manage Listings** — Mark books as sold, edit, or remove listings
- 📱 **Responsive UI** — Clean, modern interface built with Tailwind CSS and shadcn/ui
- ⚡ **Fast & Async Backend** — FastAPI with async SQLAlchemy for high performance
---
 
## 🛠️ Tech Stack
 
**Frontend**
- React + Vite
- Tailwind CSS
- shadcn/ui
- 13+ pages/routes
**Backend**
- FastAPI (Python)
- SQLAlchemy (async)
- PostgreSQL (hosted on Supabase)
- JWT Authentication
- WebSockets for real-time chat
**Deployment**
- Frontend: [Vercel](https://vercel.com)
- Backend: [Render](https://render.com)
- Database: [Supabase](https://supabase.com) (PostgreSQL, connection pooler on port 6543)
---
 
## 🚀 Getting Started (Local Setup)
 
### Prerequisites
- Node.js (v18+)
- Python 3.11.9
- PostgreSQL database (or Supabase project)
### 1. Clone the repository
```bash
git clone https://github.com/adarsh23222/BookBridge.git
cd BookBridge
```
 
### 2. Backend Setup
```bash
cd backend
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```
 
Create a `.env` file in the `backend` folder:
```env
DATABASE_URL=postgresql+asyncpg://<user>:<password>@<supabase-pooler-host>:6543/postgres
JWT_SECRET=your_secret_key_here
```
 
Run the backend:
```bash
uvicorn main:app --reload
```
 
### 3. Frontend Setup
```bash
cd frontend
npm install
```
 
Create a `.env` file in the `frontend` folder:
```env
VITE_API_URL=http://localhost:8000
```
 
Run the frontend:
```bash
npm run dev
```
 
The app should now be running at `http://localhost:5173` (or the port shown in your terminal).
 
---
 
## 🌐 Deployment Notes
 
- **Backend (Render):** Pin Python version to `3.11.9` (via `runtime.txt`) to avoid compatibility issues. `bcrypt` is pinned to `4.0.1` for compatibility with `passlib`.
- **Database (Supabase):** Use the connection pooler URL (port `6543`) instead of the direct connection string when deploying on Render's free tier.
- **CORS:** Ensure the deployed backend's CORS settings include your Vercel frontend URL.
- **Keep-alive:** Free-tier Supabase projects pause after ~7 days of inactivity, and free-tier Render services spin down after 15 minutes of inactivity. A periodic health-check ping (e.g., via [cron-job.org](https://cron-job.org)) is recommended to keep both active.
---
 
## 📂 Project Structure
 
```
BookBridge/
├── backend/
│   ├── main.py
│   ├── database.py
│   ├── models/
│   ├── routes/
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── pages/
│   │   ├── components/
│   │   └── App.jsx
│   └── package.json
└── README.md
```
 
---
 
## 🧑‍💻 Author
 
**Adarsh Pal**
- GitHub: [@adarsh23222](https://github.com/adarsh23222)
- LinkedIn: [adarsh-pal](https://www.linkedin.com/in/adarsh-pal-5428b9324)
---
 
## 📄 License
 
This project is open-source and available for learning purposes.
