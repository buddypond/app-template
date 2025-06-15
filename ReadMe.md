# 🧪 BuddyPond App Template

This is a ready-to-deploy template for building and hosting BuddyPond Apps.

By forking this repo and connecting your GitHub account to BuddyPond, you can automatically publish your static app files to your BuddyPond App using GitHub Actions.

![buddy-the-frog-256](https://github.com/user-attachments/assets/0f7a8018-ad37-493a-908d-68765929dfab)


---

## 🚀 How It Works

This repo includes a pre-configured [BuddyPond Upload Action](https://github.com/buddypond/upload-action) that uploads your app files (like `index.html`, images, CSS, JavaScript, etc.) to your personal BuddyPond storage space whenever you push to the `main` branch.

---
![buddy-apps](https://github.com/user-attachments/assets/c50e1ed4-4595-4775-8f40-d4b013ceb6d5)


___

## ✅ Quick Start

### 1. Fork this repo

Click **“Use this template”** to create your own copy under your GitHub account.

---

### 2. Generate a BuddyPond API Key

Inside your BuddyPond account:

1. Open your `Profile`
2. Navigate to `API Keys`
3. Create a new API Key with the `deploy` permissions
4. Copy the newly generated API Key

[generate-api-keys.webm](https://github.com/user-attachments/assets/504454d1-134a-4fad-a672-e78ccb7afc60)


---

### 3. Add Your BuddyPond API Key to Github

In your new Github repo:

1. Go to **Settings** → **Secrets and variables** → **Actions** → **New repository secret**
2. Create a secret named `BP_API_KEY`
3. Copy in your BuddyPond API Key

---

### 3. Configure Your Upload Target

In `.github/workflows/deploy.yml`, update this section with your BuddyPond info:

```yaml
- uses: buddypond/upload-action@v1
  with:
    bp_api_key: ${{ secrets.BP_API_KEY }}
    user: YourBuddypondUsername
    folder: pads/your_app_folder
```

Note: Your target `folder` can be any path within your  `Buddy Files` home. We recommend uploading to the `pads` directory.

## Storage Limitations

Free BuddyPond accounts default to `10mb` of storage per user. Storage limits are linked to 1:1 to your `BuddyCoin` balance of `$MEGA` coins. You can acquire more `$MEGA` within BuddyPond.

