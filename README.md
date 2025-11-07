<!-- PROFILE README FOR Ishaq Ahnaf Khan -->
<h1 align="center">Hi, I'm Ishaq Ahnaf Khan</h1>
<p align="center">
  <b>ML/AI • Full-Stack JS • Pythonic data wrangler</b><br/>
  I build data-driven apps and ship fast with React, Node.js, and Python.
</p>

<p align="center">
  <a href="https://github.com/YOUR_GITHUB_USERNAME?tab=followers"><img src="https://img.shields.io/github/followers/YOUR_GITHUB_USERNAME?style=flat&label=Followers"/></a>
  <img src="https://komarev.com/ghpvc/?username=YOUR_GITHUB_USERNAME&style=flat&label=Profile+Views"/>
  <a href="mailto:your.email@example.com"><img src="https://img.shields.io/badge/Email-Contact-blue"/></a>
  <a href="https://www.linkedin.com/in/YOUR_LINKEDIN/"><img src="https://img.shields.io/badge/LinkedIn-Connect-informational"/></a>
</p>

---

### 🧠 What I’m good at (no fluff)
**Languages & Core:**  
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)

**Frontend:**  
![React](https://img.shields.io/badge/React-20232A?logo=react&logoColor=61DAFB)
![TailwindCSS](https://img.shields.io/badge/Tailwind-38B2AC?logo=tailwindcss&logoColor=white)

**Backend & Tools:**  
![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?logo=express&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?logo=vercel&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)

**Data/ML:**  
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)

---

### 🚀 Quick Demos
- **ML pipeline (sklearn + Pandas):** feature engineering → model → metrics  
- **Full-stack app:** React + Tailwind frontend, Node/Express API, JSON storage or Postgres  
- **Data viz:** Jupyter/Matplotlib dashboards, exportable reports

> Want proof instead of promises? Scroll down and click the collapsibles.

---

<details>
  <summary><b>📦 Minimal API: Express + JSON (click to expand)</b></summary>

```js
// server.js — dead simple API that you can deploy on Vercel/Render
import express from "express";
import fs from "fs";

const app = express();
app.use(express.json());

const DB = "./db.json";
const read = () => JSON.parse(fs.existsSync(DB) ? fs.readFileSync(DB) : "{}");
const write = (data) => fs.writeFileSync(DB, JSON.stringify(data, null, 2));

app.get("/api/notes", (req, res) => res.json(read()));
app.post("/api/notes", (req, res) => {
  const db = read();
  const id = Date.now().toString();
  db[id] = req.body;
  write(db);
  res.status(201).json({ id, ...req.body });
});

app.listen(3000, () => console.log("API on http://localhost:3000"));
