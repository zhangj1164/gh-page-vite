# Vite + React + gh-pages Demo

This is a demo project to show how to use gh-pages library to deploy Vite + React applications to GitHub Pages.

## Features

- Vite + React setup
- gh-pages deployment configuration
- Simple counter app for demonstration

## Getting Started

### Installation

```bash
npm install
```

### Local Development

```bash
npm run dev
```

Open your browser and navigate to the URL shown in the terminal (usually http://localhost:5173).

### Build for Production

```bash
npm run build
```

This will generate a `dist` directory with the production build of your application.

## Deploying to GitHub Pages

### Step 1: Create a GitHub Repository

1. Go to [GitHub](https://github.com/) and create a new repository.
2. Do not initialize it with a README, .gitignore, or license (we already have these files).

### Step 2: Initialize Git in Your Project

```bash
git init
```

### Step 3: Add Remote Repository

```bash
git remote add origin https://github.com/your-username/your-repository-name.git
```

### Step 4: Commit Your Changes

```bash
git add .
git commit -m "Initial commit"
```

### Step 5: Push to GitHub

```bash
git push -u origin main
```

### Step 6: Deploy with gh-pages

```bash
npm run deploy
```

This command will:
1. Build your application (if not already built)
2. Create a `gh-pages` branch in your repository
3. Push the contents of the `dist` directory to this branch
4. Set up GitHub Pages to serve from this branch

### Step 7: Access Your Deployed Application

After deployment, your application will be available at:
```
https://your-username.github.io/your-repository-name/
```

## How gh-pages Works

1. The `gh-pages` library creates a separate branch in your Git repository called `gh-pages`.
2. It copies the contents of your build directory (in this case, `dist`) to this branch.
3. GitHub Pages automatically serves any static content from the `gh-pages` branch.
4. The deployment process is triggered by running `npm run deploy`.

## Project Configuration

### package.json

```json
{
  "scripts": {
    "deploy": "gh-pages -d dist"
  },
  "devDependencies": {
    "gh-pages": "^6.1.1"
  }
}
```

### vite.config.js

```javascript
export default defineConfig({
  base: './'
})
```

The `base: './'` configuration ensures that all assets are loaded correctly from the GitHub Pages URL.

## Notes

- Make sure you have the correct repository URL in the `git remote add` command.
- The first deployment might take a few minutes for GitHub Pages to process.
- Subsequent deployments will update the existing `gh-pages` branch.
- You can check the deployment status in your GitHub repository's Settings > Pages.

## License

MIT