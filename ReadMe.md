# 🧪 BuddyPond App Template

This is a ready-to-deploy template for building and hosting BuddyPond Apps.

By forking this repo and connecting your GitHub account to BuddyPond, you can automatically publish your static app files to your BuddyPond Pad using GitHub Actions.

---

## 🚀 How It Works

This repo includes a pre-configured [BuddyPond Upload Action](https://github.com/buddypond/upload-action) that uploads your app files (like `index.html`, images, CSS, JavaScript, etc.) to your personal BuddyPond storage space whenever you push to the `main` branch.

---

## ✅ Quick Start

### 1. Fork this repo

Click **“Use this template”** to create your own copy under your GitHub account.

---

### 2. Add Your BuddyPond API Key

In your new repo:

1. Go to **Settings** → **Secrets and variables** → **Actions** → **New repository secret**
2. Create a secret named `BP_API_KEY`
3. You can generate your API key from **BuddyPond → Profile → API Keys**

---

### 3. Configure Your Upload Target

In `.github/workflows/deploy.yml`, update this section with your BuddyPond info:

```yaml
- uses: buddypond/upload-action@v1
  with:
    bp_api_key: ${{ secrets.BP_API_KEY }}
    user: YourBuddypondUsername
    folder: pads/your_app_folder
