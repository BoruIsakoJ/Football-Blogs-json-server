# Deploying `db.json` to Render using `json-server`

This guide will help you deploy a fake REST API using `json-server` and host it for free on [Render](https://render.com). This is perfect for prototyping or mock backend APIs for development.

## 📦 Requirements

- Node.js installed
- A free [Render](https://render.com) account
- `db.json` file ready with your mock data (e.g., blog posts)

---

## 🚀 Deployment Steps

### 1. Create a project folder

```bash
mkdir < project-name -json-server
cd <project-name -json-server
```

### 2. Initialize a Node.js project

```bash
npm init -y
```

### 3. Install `json-server`

```bash
npm install json-server@0.17.4
```

### 4. Create your `db.json`

In the root of your project, add a file named `db.json` and paste your mock data. Example:

```json
{
  "posts": [
    {
      "id": 1,
      "title": "Top 10 Football Players in 2024",
      "author": "John Doe",
      "authorImage": "https://example.com/john.jpg",
      "date": "2024-04-21",
      "image": "https://example.com/messi.jpg",
      "content": "Here's our list of top players..."
    }
  ]
}
```


### 5. Push to GitHub

Create a new GitHub repository and push your project:

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/your-username/football-blogs-json-server.git
git push -u origin main
```

### 6. Deploy to Render

1. Go to [https://render.com](https://render.com)
2. Click **"New" > "Web Service"**
3. Connect your GitHub repository
4. Set the following options:
   - **Build Command**: `npm install`
   - **Start Command**: `node server.js`
   - **Environment**: `Node`


Render will build and deploy your app.

---

## ✅ Done!

Your API should now be live at:

```
https://<your-app-name>.onrender.com/api/posts
```

Example:

```
https://football-blogs-json-server.onrender.com/api/posts
```

Update your frontend `fetch()` calls to use:

```js
fetch("https://football-blogs-json-server.onrender.com/api/posts")
```

Happy coding! ⚽🔥
