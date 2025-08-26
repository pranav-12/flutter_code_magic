# 🔑 Codemagic Credentials Setup Checklist

## ✅ **Ready to Configure** (You have these)

### 📁 **Google Drive Folder IDs** → `google_credentials` group
```bash
GOOGLE_DRIVE_DEMO_ANDROID_FOLDER_ID=1cOk2_gfl1Tlv6fuzTRa1e6-77CglMAOP
GOOGLE_DRIVE_DEMO_IOS_FOLDER_ID=1KARIQrBFkdJRgOxhY3Si2UAV62TRj_LP
GOOGLE_DRIVE_PROD_ANDROID_FOLDER_ID=1vXto-9QTNCB-DijFbNnRj-B4nzU9bYhp
GOOGLE_DRIVE_PROD_IOS_FOLDER_ID=1jGiQflfwote8PboFIEK9raTM6X_m8kBs
GOOGLE_DRIVE_STAGING_ANDROID_FOLDER_ID=1vXto-9QTNCB-DijFbNnRj-B4nzU9bYhp
GOOGLE_DRIVE_STAGING_IOS_FOLDER_ID=1jGiQflfwote8PboFIEK9raTM6X_m8kBs
```

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
SLACK_WEBHOOK_URL=https://hooks.slack.com/services/YOUR/WEBHOOK/URL
```
**How to get:**
1. Go to your Slack workspace
2. Create app → Enable Incoming Webhooks
3. Create webhook for your channel
4. Copy the webhook URL

### 🏪 **Google Play Store** → `google_play_credentials` group
```bash
GOOGLE_PLAY_SERVICE_ACCOUNT={play_store_json_here}
```
**How to get:**
1. Go to [Google Play Console](https://play.google.com/console)
2. Setup → API access → Create service account
3. Download JSON key, grant permissions

### 🍎 **App Store Connect** → `app_store_credentials` group
```bash
APP_STORE_CONNECT_ISSUER_ID=your_issuer_id
APP_STORE_CONNECT_KEY_ID=your_key_id
APP_STORE_CONNECT_PRIVATE_KEY=your_private_key
```
**How to get:**
1. Go to [App Store Connect](https://appstoreconnect.apple.com)
2. Users and Access → Keys → Create API key
3. Download .p8 file, note Key ID and Issuer ID

## 🔧 **Android Signing** (Already configured)
Your keystore is already set up in `android/app/build.gradle`:
- Keystore: `/Users/pranavnandhakumar/Projects/edge_credentials/abihbus_hpy.jks`
- Alias: `abhibus.com`
- Password: `AbhiBus#007`

**In Codemagic:** Upload keystore as `abhibus_edge_keystore`

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
