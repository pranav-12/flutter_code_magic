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

### 🔐 **Google Drive Service Account** → `google_credentials` group
```bash
GOOGLE_DRIVE_SERVICE_ACCOUNT={
  "type": "service_account",
  "project_id": "codemagic-470112",
  "private_key_id": "f8d7af9213beb8fc686d825fade79de89c2e6d24",
  "private_key": "-----BEGIN PRIVATE KEY-----\nMIIEvgIBADANBgkqhkiG9w0BAQEFAASCBKgwggSkAgEAAoIBAQC4K4kdpOF+WqV5\nQEl5i6GrVm47qYeBlct0gURfVnz08x9rRXu9bBnqDsVjPl0wrEh5m9cZrZSjBpQ0\nxyXlXpOTkz0vFFbXT7Up94wzaviAwaWaDFt1IghZoHpSb3dZNGjCU1RisRi/OkQF\n0paJ6BmsPm0YG1P8KSwmF6TQ864OPQS1XOS4/33J+79kDqY2YimJuGDmgUZzMB9m\nlGYYQdwGGSHLtJJ6KyC8xqMrvFdMDcSML6gazwyu+2mnJOFXH2PN50D/DO3CVGTG\nH7rrrpRd6+sd59SfIpwLcKvEyzHtMlwtzpNvwn2iIZUOhSYxdY7WQbnDea0kjwuw\nyP+HiDwfAgMBAAECggEASE0rHLysm965RLM0xSdIlkutpfWFkZ19jKTs8yKwlrdV\nl9bk37XvLICVBEOo8SFJqJhCJz4Kcr/z8g5Wtcfd1ttAc1mgSBHuNOYOn+b4XQ/o\n0+PTCdaNAaarLu68o4QcNmHhaIdPCE+3AbQtTkGUxpaRXJvp6j49q0yv8yofJE4r\niC34WybyobhRKKW3BDhV1cPs4Vt7gupxR0bCxyp99j/DPQhqb7jk+tTlf4KyM0Qy\n7XLu/6OEwpf4RdEM/hU4i1hHUqvbqueFQsVehVfJOd1Z4nMS8UiopL/yCnR0Vw35\nEYXTJoFgygk8US3aVhFEdJRTGUozgkxOPLZs1gQ0wQKBgQDzxCvwCQkpZqg/NM1I\nBZYG+JHpqILTDIZ+VIBkegdq/gy3LvsE7VmzeYN8dkml/kOfbfPCAl4xYe+e1/5Z\ngTX0JpjD4avxIj1Itv2LWDjdO1AQndte5unSEwwcmgzFnGUQj3Hznx3KeJtgbX9l\ne1lUBM5AbjYtTxfulJKb1tCLXwKBgQDBabD84AINjo4A1tNS26+kepiKrofK7sPQ\n1/gs6+QIsp68s8M8EVRh6FCntlEURwZLzrMYlNJDgwIFyQhxi8/J4o0NkfY7+YjP\n7afAosFGgQi4NZU26AVZDtbZAJm1nhsUJu1pKTp5oHoWfwBk/13UiwbaNzJT2sfM\nYVgFJoLHQQKBgQC/qNYC/Je/fX97csCUiA/Vm0reNCfoWEjGuxnX5jo+3VCSFtY2\noYeNnVTMXxS49pmkmIa3W7VDjoUglyLcrMMHG/Gw0ZanGQymR3pCPTM4fpIM/pCk\npVniWieDtXulQ7oSszYdHlYGA53myzEHUVyCuuSPtBfUuANRCm/bJ6MAcQKBgCh6\nikQiTcuwjh+21jt9JuFxlwNPS7Q5DFplGNet9uerGnW72Zx0tAhZqqevDIEF7Fdp\nRypZ2zet73pufInnDPHfrE2uwq4Cp5N81aMHbRPoZX7IGBaJsLTW2jhIW+Ma1+f7\nzaw4qLhT0blrkxWQLH8TKbf53VqXa0FnDhjl2nEBAoGBAJUnEVBKt15fY9zvp96k\nno/7qPnObMLLLOGpe8Xg98/V0gYY3JYraw9zxDxdCd2L5FD0ZwU2khfQMxxOlHmZ\n8qy0NkT4QOvLW2+QD6t8P+kWofwE/GMHtTQlPXa/u/SwAe+bGEq0C27qLJSjpOXn\nx7nSahj3SZDJtr3El4JpQ4Dr\n-----END PRIVATE KEY-----\n",
  "client_email": "edge-app-cicd@codemagic-470112.iam.gserviceaccount.com",
  "client_id": "117036156253709595268",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token",
  "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
  "client_x509_cert_url": "https://www.googleapis.com/robot/v1/metadata/x509/edge-app-cicd%40codemagic-470112.iam.gserviceaccount.com",
  "universe_domain": "googleapis.com"
}

```
**How to get:**
1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create/select project → Enable Google Drive API
3. Create service account → Download JSON key
4. Share all your Google Drive folders with the service account email

## 🚧 **Still Need to Setup**

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
4. **Store Credentials** (for staging deployments only)

Once you have the Google Drive service account, you can start testing your CI/CD pipeline!
