# Flask Database API

A Flask REST API for managing FAQs, courses, users, and student feedback.

## Features

- ✅ FAQ query endpoint
- ✅ Course management
- ✅ User management
- ✅ Unanswered questions tracking
- ✅ Student feedback counts
- ✅ Interactive dashboard UI

## Deployment to Render

### Step 1: Push to GitHub

1. Initialize git (if not already done):
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. Create a repository on GitHub and push:
   ```bash
   git remote add origin <your-github-repo-url>
   git branch -M main
   git push -u origin main
   ```

### Step 2: Deploy on Render

1. Go to [Render Dashboard](https://dashboard.render.com/)
2. Click **"New +"** → **"Web Service"**
3. Connect your GitHub repository
4. Configure the service:
   - **Name**: `flask-database-api` (or your preferred name)
   - **Environment**: `Python 3`
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn app:app`
   - **Plan**: Free tier is fine for testing

5. Click **"Create Web Service"**

### Step 3: Environment Variables (Optional)

If you want to use environment variables for database credentials (recommended for security):

1. In Render dashboard, go to **Environment** tab
2. Add these variables:
   - `DB_HOST=34.170.34.174`
   - `DB_USER=root`
   - `DB_PASSWORD=Psau_2025`
   - `DB_NAME=psau_admission`
   - `DB_PORT=3306`

Then update `app.py` to use `os.environ.get()` for these values.

### Step 4: Verify Deployment

Once deployed, your app will be available at:
`https://your-app-name.onrender.com`

Test endpoints:
- Health: `https://your-app-name.onrender.com/health`
- Users: `https://your-app-name.onrender.com/users`
- Dashboard: `https://your-app-name.onrender.com/`

## Local Development

```bash
# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
```

The app will be available at `http://localhost:5000`

## API Endpoints

- `GET /health` - Health check
- `GET /users` - Get all users
- `GET /courses` - Get all courses
- `GET /faqs?question=<query>` - Search FAQs
- `GET /faqs/list` - Get all FAQs
- `GET /unanswered_questions` - Get unanswered questions
- `POST /unanswered_questions` - Save unanswered question
- `GET /student_feedback_counts` - Get feedback counts
- `POST /student_feedback_counts` - Add feedback count

