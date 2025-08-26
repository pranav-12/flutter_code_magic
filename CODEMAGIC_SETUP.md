# Codemagic CI/CD Setup Guide for Edge App

This guide will help you configure Codemagic CI/CD for the Edge Flutter application with automated builds, testing, and deployment.

## 🏗️ Build Configuration Overview

### Build Types
1. **Demo Builds** (Testing)
   - Version: 3.5.1+35
   - Flavor: `demo`
   - Platforms: Android, iOS, Web
   - Deployment: Google Drive + Diawi (iOS)

2. **Prod Builds** (Testing)
   - Version: 3.5.1+35
   - Flavor: `prod`
   - Platforms: Android, iOS, Web
   - Deployment: Google Drive + Diawi (iOS)

3. **Staging Builds** (Store Ready)
   - Version: 3.5.1+16
   - Flavor: `prod`
   - Platforms: Android, iOS, Web
   - Deployment: Play Store + App Store + Google Drive + Diawi (iOS)

### File Naming Convention
- **Android APK**: `edge_{flavor}_v{version}+{code}.apk`
  - Example: `edge_demo_v3.5.1+35.apk`
- **Android AAB**: `edge_{flavor}_v{version}+{code}.aab`
  - Example: `edge_staging_v3.5.1+16.aab`
- **iOS IPA**: `edge_{flavor}_v{version}+{code}.ipa`
  - Example: `edge_prod_v3.5.1+35.ipa`
- **Web**: `edge_{flavor}_web_v{version}+{code}.tar.gz`
  - Example: `edge_demo_web_v3.5.1+35.tar.gz`

## 🔧 Codemagic Setup Instructions

### 1. Connect Repository
1. Log in to [Codemagic](https://codemagic.io)
2. Connect your Git repository
3. Import the project and detect the `codemagic.yaml` file

### 2. Configure Environment Variables

Navigate to **App Settings > Environment Variables** and add the following:

#### Required Groups
Create these environment variable groups:

**google_credentials**
- `GOOGLE_DRIVE_SERVICE_ACCOUNT` - Service account JSON for Google Drive API
- `GOOGLE_DRIVE_DEMO_ANDROID_FOLDER_ID` - Google Drive folder ID for demo Android builds
- `GOOGLE_DRIVE_DEMO_IOS_FOLDER_ID` - Google Drive folder ID for demo iOS builds
- `GOOGLE_DRIVE_PROD_ANDROID_FOLDER_ID` - Google Drive folder ID for prod Android builds
- `GOOGLE_DRIVE_PROD_IOS_FOLDER_ID` - Google Drive folder ID for prod iOS builds
- `GOOGLE_DRIVE_STAGING_ANDROID_FOLDER_ID` - Google Drive folder ID for staging Android builds
- `GOOGLE_DRIVE_STAGING_IOS_FOLDER_ID` - Google Drive folder ID for staging iOS builds

**slack_credentials**
- `SLACK_WEBHOOK_URL` - Slack webhook URL for notifications

**diawi_credentials**
- `DIAWI_TOKEN` - Diawi API token for iOS app distribution
  - Your token: `1NAtEax0BNyeL1V3Jc5hC8kpFMigx3PcIo0gya4l9e`

**google_play_credentials**
- `GOOGLE_PLAY_SERVICE_ACCOUNT` - Service account JSON for Google Play Store API

**app_store_credentials**
- `APP_STORE_CONNECT_ISSUER_ID` - App Store Connect API issuer ID
- `APP_STORE_CONNECT_KEY_ID` - App Store Connect API key ID
- `APP_STORE_CONNECT_PRIVATE_KEY` - App Store Connect API private key

### 3. Configure Code Signing

#### Android Signing
1. Go to **App Settings > Code Signing > Android**
2. Upload your keystore file (`abihbus_hpy.jks`)
3. Set the keystore alias name as: `abhibus_edge_keystore`
4. Enter keystore password: `AbhiBus#007`
5. Enter key alias: `abhibus.com`
6. Enter key password: `AbhiBus#007`

#### iOS Signing
1. Go to **App Settings > Code Signing > iOS**
2. Upload your certificates and provisioning profiles
3. Configure for both Ad Hoc and App Store distribution
4. Bundle ID: `com.abhibus.edge`

### 4. Configure Webhooks (Optional)
Set up webhooks for automatic builds:
- **Demo builds**: Trigger on push to `demo/**` branches
- **Prod builds**: Trigger on push to `prod/**` branches
- **Staging builds**: Trigger on push to `staging/**` branches

## 🔑 Setting Up Service Accounts

### Google Drive API Setup
1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create a new project or select existing
3. Enable Google Drive API
4. Create a service account
5. Download the JSON key file
6. Share your Google Drive folders with the service account email
7. Copy the JSON content to `GOOGLE_DRIVE_SERVICE_ACCOUNT` variable

### Google Play Store API Setup
1. Go to [Google Play Console](https://play.google.com/console)
2. Navigate to **Setup > API access**
3. Create a service account
4. Download the JSON key file
5. Grant necessary permissions
6. Copy the JSON content to `GOOGLE_PLAY_SERVICE_ACCOUNT` variable

### App Store Connect API Setup
1. Go to [App Store Connect](https://appstoreconnect.apple.com)
2. Navigate to **Users and Access > Keys**
3. Create a new API key
4. Download the `.p8` file
5. Note the Key ID and Issuer ID
6. Set up the environment variables accordingly

### Diawi Setup
1. Go to [Diawi](https://www.diawi.com)
2. Create an account
3. Go to API settings
4. Generate an API token
5. Add it to `DIAWI_TOKEN` variable

### Slack Webhook Setup
1. Go to your Slack workspace
2. Create a new app or use existing
3. Enable Incoming Webhooks
4. Create a webhook for your desired channel
5. Copy the webhook URL to `SLACK_WEBHOOK_URL` variable

## 📁 Google Drive Folder Structure

Create the following folder structure in Google Drive:
```
Edge App Builds/
├── Demo/
├── Prod/
└── Staging/
```

Get the folder IDs from the URL when you open each folder and add them to the respective environment variables.

**Your actual folder IDs:**
- **Demo Android**: `1cOk2_gfl1Tlv6fuzTRa1e6-77CglMAOP`
- **Demo iOS**: `1KARIQrBFkdJRgOxhY3Si2UAV62TRj_LP`
- **Prod Android**: `1vXto-9QTNCB-DijFbNnRj-B4nzU9bYhp`
- **Prod iOS**: `1jGiQflfwote8PboFIEK9raTM6X_m8kBs`
- **Staging Android**: Use prod Android folder or create new
- **Staging iOS**: Use prod iOS folder or create new

### 🔧 **Environment Variables to Set in Codemagic:**

Copy these exact values into your Codemagic `google_credentials` environment group:

```bash
# Your actual folder IDs - ready to copy/paste
GOOGLE_DRIVE_DEMO_ANDROID_FOLDER_ID=1cOk2_gfl1Tlv6fuzTRa1e6-77CglMAOP
GOOGLE_DRIVE_DEMO_IOS_FOLDER_ID=1KARIQrBFkdJRgOxhY3Si2UAV62TRj_LP
GOOGLE_DRIVE_PROD_ANDROID_FOLDER_ID=1vXto-9QTNCB-DijFbNnRj-B4nzU9bYhp
GOOGLE_DRIVE_PROD_IOS_FOLDER_ID=1jGiQflfwote8PboFIEK9raTM6X_m8kBs

# For staging, you can reuse prod folders or create new ones
GOOGLE_DRIVE_STAGING_ANDROID_FOLDER_ID=1vXto-9QTNCB-DijFbNnRj-B4nzU9bYhp
GOOGLE_DRIVE_STAGING_IOS_FOLDER_ID=1jGiQflfwote8PboFIEK9raTM6X_m8kBs
```

## 🚀 Triggering Builds

### Branch Naming Convention
- **Demo builds**: Push to branches matching `demo/**`
  - Example: `demo/feature-update`, `demo/v3.5.1`
- **Prod builds**: Push to branches matching `prod/**`
  - Example: `prod/release-candidate`, `prod/v3.5.1`
- **Staging builds**: Push to branches matching `staging/**`
  - Example: `staging/v3.5.1`, `staging/store-release`

### Manual Builds
You can also trigger builds manually from the Codemagic dashboard:
1. Go to your app in Codemagic
2. Select the desired workflow
3. Click "Start new build"
4. Choose the branch and any additional options

## 📱 Build Outputs

### Demo & Prod Builds
- ✅ Build and test
- ✅ Upload to Google Drive
- ✅ Upload iOS to Diawi
- ✅ Send Slack notification
- ❌ No store deployment

### Staging Builds
- ✅ Build and test
- ✅ Upload to Google Drive
- ✅ Upload iOS to Diawi
- ✅ Deploy Android to Google Play Store (Internal track)
- ✅ Deploy iOS to App Store Connect (TestFlight)
- ✅ Send Slack notification

## 🔍 Testing Pipeline

Each build includes:
1. **Flutter analyze** - Static code analysis
2. **Flutter test** - Unit tests
3. **Build validation** - File size and integrity checks
4. **Basic APK/IPA validation** - Ensures builds are valid

## 📧 Slack Notifications

Notifications include:
- 🚀 Build completion status
- 📱 Platform and version information
- 📁 Google Drive links
- 📲 Diawi links (for iOS)
- 🏪 Store deployment status
- 📊 Build size information

## 🔧 Troubleshooting

### Common Issues

1. **Build fails with "Flutter not found"**
   - Ensure Flutter SDK is properly configured in Codemagic

2. **iOS build fails with code signing errors**
   - Verify certificates and provisioning profiles are correctly uploaded
   - Check bundle ID matches in all configurations

3. **Android build fails with keystore errors**
   - Verify keystore file is uploaded with correct passwords
   - Check keystore alias name matches configuration

4. **Google Drive upload fails**
   - Verify service account JSON is valid
   - Ensure folders are shared with service account email
   - Check folder IDs are correct

5. **Diawi upload fails**
   - Verify Diawi token is valid
   - Check IPA file size (Diawi has limits)

6. **Slack notifications not working**
   - Verify webhook URL is correct
   - Check webhook permissions in Slack

### Build Size Optimization
- Ensure `--release` flag is used for production builds
- Consider using `--split-per-abi` for Android APKs if needed
- Enable ProGuard/R8 for Android builds
- Use `--tree-shake-icons` for Flutter builds

## 📚 Additional Resources

- [Codemagic Documentation](https://docs.codemagic.io/)
- [Flutter Build Documentation](https://flutter.dev/docs/deployment)
- [Google Play Console Help](https://support.google.com/googleplay/android-developer/)
- [App Store Connect Help](https://developer.apple.com/support/app-store-connect/)
- [Diawi Documentation](https://www.diawi.com/docs)

## 🔄 Maintenance

### Regular Tasks
1. Update version numbers in `codemagic.yaml` for releases
2. Rotate API keys and certificates before expiration
3. Monitor build times and optimize if needed
4. Clean up old builds in Google Drive periodically
5. Update Flutter SDK version as needed

### Version Updates
When updating app versions:
1. Update `VERSION_NAME` and `VERSION_CODE` in `codemagic.yaml`
2. Update version in `pubspec.yaml`
3. Commit changes and push to trigger builds

This setup provides a comprehensive CI/CD pipeline that handles building, testing, and distributing your Edge app across all platforms while maintaining clean file organization and proper notifications.
