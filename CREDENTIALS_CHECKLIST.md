# 🔑 Codemagic Credentials Setup Checklist

## ✅ **Ready to Configure** (You have these)

### 📁 **Google Drive Folder ID** → `google_credentials` group
```bash
GOOGLE_DRIVE_FOLDER_ID=1GNT1C0eOcg0hgsxr6lqIKx-LwZK77BBF
```
**✅ Your folder:** https://drive.google.com/drive/folders/1GNT1C0eOcg0hgsxr6lqIKx-LwZK77BBF

### 📲 **Diawi Token** → `diawi_credentials` group
```bash
DIAWI_TOKEN=1NAtEax0BNyeL1V3Jc5hC8kpFMigx3PcIo0gya4l9e
```

## 🚧 **Still Need to Setup**

### 🔐 **Google Drive Service Account** → `google_credentials` group
```bash
GOOGLE_DRIVE_SERVICE_ACCOUNT={paste_your_json_here}
```
**How to get:**
1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create/select project → Enable Google Drive API
3. Create service account → Download JSON key
4. Share all your Google Drive folders with the service account email

### 💬 **Slack Webhook** → `slack_credentials` group
```bash
SLACK_WEBHOOK_URL=https://hooks.slack.com/services/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
```
**✅ Your webhook:** Already provided
**How to get:**
1. Go to your Slack workspace
2. Create app → Enable Incoming Webhooks
3. Create webhook for your channel
4. Copy the webhook URL

## 📋 **Setup Progress**

- [x] Google Drive folder IDs
- [x] Diawi token
- [x] Android keystore info
- [ ] Google Drive service account
- [ ] Slack webhook
- [ ] Google Play Store credentials
- [ ] App Store Connect credentials
- [ ] iOS certificates & provisioning profiles

## 🚀 **Priority Order**

1. **Google Drive Service Account** (required for file uploads)
2. **Slack Webhook** (for notifications)
3. **iOS Certificates** (for iOS builds)
4. **Store Credentials** (for staging deployments only)

Once you have the Google Drive service account, you can start testing your CI/CD pipeline!
