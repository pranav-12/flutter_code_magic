# 🔑 Codemagic Credentials Setup Checklist

## ✅ **Ready to Configure** (You have these)

### 📁 **Google Drive Folder ID** → `google_credentials` group
```bash
GOOGLE_DRIVE_FOLDER_ID=1GNT1C0eOcg0hgsxr6lqIKx-LwZK77BBF
```
**✅ Your folder:** https://drive.google.com/drive/folders/1GNT1C0eOcg0hgsxr6lqIKx-LwZK77BBF

### 📲 **Diawi Token** → `diawi_credentials` group
```bash
DIAWI_TOKEN=W628xkAOs8aRELyJlllM9ouhcaEYymIIM3O9i2Wpj2
```

### 🔐 **Google Drive Service Account** → `google_credentials` group
```bash
GOOGLE_DRIVE_SERVICE_ACCOUNT={paste_your_service_account_json_here}
```
**✅ You have this:** Use your actual service account JSON (keep it secure!)
**How to get:**
1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create/select project → Enable Google Drive API
3. Create service account → Download JSON key
4. Share your Google Drive folder with the service account email

### 💬 **Slack Webhook** → `slack_credentials` group
```bash
SLACK_WEBHOOK_URL=https://hooks.slack.com/services/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
```
**✅ Your webhook:** Already provided

## 📋 **Setup Progress**

- [x] Google Drive folder ID
- [x] Diawi token  
- [x] Google Drive service account
- [x] Slack webhook
- [ ] Android keystore info
- [ ] Google Play Store credentials
- [ ] App Store Connect credentials
- [ ] iOS certificates & provisioning profiles

## 🚀 **Priority Order**

1. **Google Drive Service Account** (required for file uploads)
2. **Slack Webhook** (for notifications)
3. **iOS Certificates** (for iOS builds)
4. **Store Credentials** (for publishing only)

## 📝 **Setup Instructions**

1. **In Codemagic Dashboard:**
   - Go to your app → Environment variables
   - Create environment groups: `google_credentials`, `slack_credentials`, `diawi_credentials`
   - Add variables to respective groups (mark as Secret)

2. **Test the Setup:**
   - Push code to trigger build
   - Check build logs for successful uploads
   - Verify files appear in Google Drive
   - Check Slack for notifications

Once you configure these environment variables in Codemagic, your CI/CD pipeline will be fully functional!
