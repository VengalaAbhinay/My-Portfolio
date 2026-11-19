# Vengala Abhinay — 3D Developer Portfolio

A high-performance, mobile-responsive 3D developer portfolio showcasing full-stack engineering, AI applications, and mobile systems. Powered by Vite and Three.js with zero heavy front-end framework overhead.

---

## ⚡ Tech Stack & Architecture

- **Core**: Vanilla HTML5, Modern CSS3, JavaScript (ESNext)
- **3D Graphics**: Three.js WebGL particles and dynamic ambient perspective camera
- **Build Tool**: [Vite](https://vitejs.dev/) for sub-second hot module reloading and optimized bundle output
- **Deployment Platform**: [Vercel](https://vercel.com/) with automated GitHub CI/CD

---

## 🛠️ Local Development

### Prerequisites
- [Node.js](https://nodejs.org/) (version 18 or higher recommended)
- `npm` (bundled with Node.js)

### 1. Clone or Open the Repository
```bash
cd abhinay-portfolio
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Start Local Development Server
```bash
npm run dev
```
Open your browser at `http://localhost:5173` to view the live site with instant hot reloading.

### 4. Build for Production
```bash
npm run build
```
Vite will compile the project into the optimized `dist/` directory.

### 5. Preview Production Build Locally
```bash
npm run preview
```

---

## 🚀 Complete Step-by-Step Vercel Deployment Guide (GitHub Integration)

Follow this guide to deploy your portfolio to **Vercel** with automatic continuous deployment (every time you push changes to GitHub, your portfolio automatically updates live).

### Step 1: Initialize Git and Commit Your Code Locally

Open your terminal in the `abhinay-portfolio` directory:

```bash
# Navigate to the project folder if you aren't already there
cd c:\Me\My_Portfolio\abhinay-portfolio

# Initialize a git repository
git init

# Stage all project files (node_modules and dist are safely ignored by .gitignore)
git add .

# Create your initial commit
git commit -m "feat: initial portfolio release with 3D canvas and responsive layout"
```

---

### Step 2: Create a GitHub Repository and Push

1. Open your browser and go to [github.com/new](https://github.com/new).
2. Set your **Repository name** (e.g., `portfolio` or `abhinay-portfolio`).
3. Set the visibility to **Public** (recommended for developer portfolios).
4. **Do not** check "Add a README file", ".gitignore", or "license" (we already have them).
5. Click **Create repository**.
6. Copy the repository remote commands and run them in your terminal:

```bash
# Rename branch to main
git branch -M main

# Link your local repo to GitHub (replace with your actual GitHub username and repo name)
git remote add origin https://github.com/VengalaAbhinay/abhinay-portfolio.git

# Push your code to GitHub
git push -u origin main
```

---

### Step 3: Connect Your GitHub Repository to Vercel

1. Go to [vercel.com](https://vercel.com) and click **Sign Up** or **Log In**.
2. Choose **Continue with GitHub** (this grants Vercel permission to access your repositories).
3. Once in your Vercel Dashboard, click the **Add New...** button in the top right corner and select **Project**.
4. In the **Import Git Repository** list, find your `abhinay-portfolio` repository and click **Import**.
   *(If your repository isn't showing up, click the account dropdown and select "Adjust GitHub App Permissions" to grant access to the repository).*

---

### Step 4: Configure Project Settings in Vercel

On the **Configure Project** screen:

| Setting | Value | Notes |
| :--- | :--- | :--- |
| **Project Name** | `abhinay-portfolio` | Choose any subdomain name you like |
| **Framework Preset** | **Vite** | Automatically detected by Vercel |
| **Root Directory** | `./` | Leave as `./` if you pushed the `abhinay-portfolio` folder directly |
| **Build Command** | `npm run build` | Default Vite build command |
| **Output Directory** | `dist` | Default output directory |
| **Install Command** | `npm install` | Default package installation |

> 💡 **Important Tip for Subfolder Repositories**: If you initialized git at the outer `My_Portfolio` folder instead of the inner `abhinay-portfolio` folder, click **Edit** next to **Root Directory** and select `abhinay-portfolio`.

---

### Step 5: Click "Deploy"

1. Click the blue **Deploy** button.
2. Vercel will clone your repository, run `npm install`, compile with `vite build`, and deploy globally on their Edge Network within 20–30 seconds.
3. You will see celebratory confetti and a live preview URL (e.g., `https://abhinay-portfolio.vercel.app`).

---

### Step 6: Automated CI/CD Workflow (Future Updates)

From this point forward, you never need to manually upload files or rebuild on Vercel:

```bash
# Make any edits to your code or index.html
git add .
git commit -m "update: added new hackathon achievement"
git push origin main
```

Vercel will detect the push via GitHub webhooks and deploy the update live in seconds.

---

## ⚙️ Production Configuration (`vercel.json`)

This repository includes a production-tuned `vercel.json` file providing:

1. **Security Headers**:
   - `X-Content-Type-Options: nosniff` (Prevents MIME-sniffing)
   - `X-Frame-Options: SAMEORIGIN` (Clickjacking protection)
   - `X-XSS-Protection: 1; mode=block` (Cross-site scripting protection)
   - `Referrer-Policy: strict-origin-when-cross-origin` (Privacy protection)

2. **Asset Performance Caching**:
   - Static photos, certificates, and SVG icons are cached for 1 year with `immutable` directives.
   - `RESUME.pdf` is cached with short stale-while-revalidate headers and served with inline viewing headers so the in-browser resume viewer modal loads instantly.

3. **SPA / Clean URL Rewrites**:
   - Ensures clean, extensionless navigation routing across all browsers.

---

## 📁 Project Structure

```
abhinay-portfolio/
├── dist/                   # Production build output (generated by npm run build)
├── node_modules/           # Dependencies (ignored by git)
├── public/                 # Static assets served as-is
│   ├── logo.png            # Photo logo / favicon
│   ├── favicon.svg         # Monogram SVG fallback favicon
│   ├── photo.jpg           # Hero profile portrait
│   ├── RESUME.pdf          # Resume document
│   ├── careconnect.png     # Project previews & screenshots
│   ├── crashaid.png
│   ├── mindspace.png
│   ├── socialmedia.png
│   ├── about1.jpg          # Carousel photos
│   ├── about2.jpg
│   ├── about3.jpg
│   ├── guvi-ai-photo*.jpg  # Hackathon & certificate showcase assets
│   └── agentathon-photo*.jpg
├── index.html              # Core application (markup, CSS styles, Three.js, modals)
├── package.json            # Project manifest & build scripts
├── vercel.json             # Vercel deployment routing & security headers
├── .gitignore              # Git ignore rules
└── README.md               # Documentation & deployment guide
```

---

## ✏️ Customization Quick Reference

- **Projects Data**: Open [index.html](file:///c:/Me/My_Portfolio/abhinay-portfolio/index.html) and locate `const P = [ ... ]` near line 5370 to add or edit project descriptions, live links, and tech stacks.
- **Project Filter Categories**: Each project has `categories: ["ai", "mern", "mobile"]` matching the interactive filter tabs in `#projects`.
- **Contact Form**: The contact form in `#contact` formats sender messages and opens a pre-composed Gmail Web tab addressed to `vengalaabhinay2006@gmail.com`.
- **Resume Document**: Replace [public/RESUME.pdf](file:///c:/Me/My_Portfolio/abhinay-portfolio/public/RESUME.pdf) with any updated PDF while keeping the same filename to update both the in-browser modal viewer and download links automatically.
