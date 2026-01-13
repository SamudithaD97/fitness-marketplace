# 🏋️ Fitness Marketplace – Full Stack Application

The **Fitness Marketplace** is a full-stack web application connecting users with fitness-related services and listings. Built with **React + TypeScript + Vite** on the frontend and **FastAPI + MongoDB** on the backend, it's designed for local development and future scalability.

---

## 🚀 Tech Stack

- **Frontend:** React, TypeScript, Vite, ESLint  
- **Backend:** Python, FastAPI, MongoDB, Uvicorn  
- **Tools:** Node.js, npm/yarn, Git, Postman

---

## 📁 Project Structure

```
fitness-marketplace/
│
├── fitness_marketplace_frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── package.json
│   ├── vite.config.ts
│   └── tsconfig.json
│
└── fitness_marketplace_backend/
    ├── app/
    │   ├── interfaces/
    │   │   └── route/
    │   ├── models/
    │   ├── services/
    │   └── main.py
    ├── requirements.txt
    └── .env
```

---

## ✅ Prerequisites

Ensure the following are installed:

- **Node.js** (v18+ LTS recommended)
- **npm** or **yarn**
- **Python 3.8+** (with pip)
- **Git**
- **MongoDB** (Atlas or local instance)
- **Postman** (optional, for API testing)
- **Visual Studio Code** (recommended)

---

## 💻 Local Setup & Running the Application

### 1. Clone the Repository

```bash
git clone <repository_url>
cd fitness-marketplace
```

### 2. Backend Setup

Navigate to the backend directory:

```bash
cd fitness_marketplace_backend
```

Install Python dependencies:

```bash
pip install -r requirements.txt
```

Create a `.env` file in the backend root directory:

```env
MONGO_URI=mongodb+srv://marketplace:abcd1234@cluster0.n4tvq3v.mongodb.net/fitness_marketplace?retryWrites=true&w=majority
MONGO_DB_NAME=fitness_marketplace
SECRET_KEY=your-super-secret-key-change-this-in-production
```

**⚠️ Security Warning:** Never commit the `.env` file. Add it to `.gitignore`:

```bash
echo ".env" >> .gitignore
```

Run the backend server:

```bash
python -m uvicorn app.main:app --reload
```

**Backend will run at:** `http://127.0.0.1:8000`

**API Documentation:** `http://127.0.0.1:8000/docs`

### 3. Frontend Setup

Open a **new terminal** and navigate to the frontend directory:

```bash
cd fitness_marketplace_frontend
```

Install dependencies:

```bash
npm install
# or
yarn install
```

Start the development server:

```bash
npm run dev
# or
yarn dev
```

**Frontend will be available at:** `http://localhost:5173`

---

## 🔗 API Endpoints

### Listings

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/v1/listings` | Get all listings |
| GET | `/api/v1/listings/{id}` | Get listing by ID |
| POST | `/api/v1/listings` | Create new listing |
| PUT | `/api/v1/listings/{id}` | Update listing |
| DELETE | `/api/v1/listings/{id}` | Delete listing |

### Example Request

```bash
# Get all listings
curl http://127.0.0.1:8000/api/v1/listings

# Create a listing
curl -X POST http://127.0.0.1:8000/api/v1/listings \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Personal Training",
    "category": "Training",
    "price": 50,
    "location": "Downtown Gym",
    "description": "One-on-one training sessions"
  }'
```

---

## 🧪 Testing with Postman

1. Open Postman
2. Create a new collection called "Fitness Marketplace"
3. Add requests for each endpoint
4. Set base URL to `http://127.0.0.1:8000`

**Example GET Request:**
```
GET http://127.0.0.1:8000/api/v1/listings
```

**Example POST Request:**
```
POST http://127.0.0.1:8000/api/v1/listings
Content-Type: application/json

{
  "title": "Yoga Classes",
  "category": "Classes",
  "price": 25,
  "location": "Zen Studio",
  "description": "Beginner-friendly yoga sessions"
}
```

---

## ⚠️ Important Notes

- The **backend server must be running** before using the frontend
- **Never commit** the `.env` file to version control
- Add `.env` to your `.gitignore` file
- Update the `SECRET_KEY` in production environments
- Use environment variables for API URLs in production
- The default MongoDB credentials in this README are examples only

---

## 🛠️ Development Tips

### Hot Reload

Both frontend and backend support hot reload:
- **Frontend:** Vite automatically reloads on file changes
- **Backend:** `--reload` flag enables auto-restart

### Code Quality

```bash
# Frontend linting
cd fitness_marketplace_frontend
npm run lint

# Backend formatting (if using black)
cd fitness_marketplace_backend
black app/
```

### Environment Variables

**Frontend (.env):**
```env
VITE_API_BASE_URL=http://127.0.0.1:8000
```

**Backend (.env):**
```env
MONGO_URI=your_mongodb_connection_string
MONGO_DB_NAME=fitness_marketplace
SECRET_KEY=your_secret_key_here
ENVIRONMENT=development
```

---

## 📦 Deployment

### Backend Deployment (Example with Heroku)

```bash
# Install Heroku CLI
heroku login
heroku create fitness-marketplace-api

# Set environment variables
heroku config:set MONGO_URI=your_mongo_uri
heroku config:set SECRET_KEY=your_secret_key

# Deploy
git push heroku main
```

### Frontend Deployment (Example with Vercel)

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
cd fitness_marketplace_frontend
vercel
```

---

## 🌱 Future Enhancements

- [ ] User authentication & authorization (JWT)
- [ ] Payment integration (Stripe/PayPal)
- [ ] Admin dashboard for listing management
- [ ] User reviews and ratings system
- [ ] Image upload functionality
- [ ] Email notifications
- [ ] Advanced search and filters
- [ ] Docker containerization
- [ ] CI/CD pipeline with GitHub Actions
- [ ] Unit and integration tests

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

This project is intended for educational and development purposes.

---

## 👥 Authors

- Your Name - *Initial work*

---

## 🙏 Acknowledgments

- FastAPI documentation
- React + Vite community
- MongoDB tutorials
- Open source contributors

---

## 📞 Support

For issues or questions:
- Open an issue on GitHub
- Email: support@fitnessmarketplace.com

---

**Made with ❤️ by the Fitness Marketplace Team**
