# Health Guide & Wellness: get your APK

The app is finished and tested. It has NO internet dependencies (no online fonts,
no CDN files), so it opens and works the same online and offline.

An APK can only be compiled with the Android SDK. Choose ONE way below.

## Way 1: build in the cloud with GitHub (no installs, easiest)

1. Create a free account at github.com and click **New repository** (name: health-guide, Public).
2. Click **uploading an existing file** and drag in EVERYTHING from this folder
   (www, resources, scripts, package.json, capacitor.config.json, .gitignore).
   Then add the workflow file: **Add file > Create new file**, name it
   `.github/workflows/build-apk.yml` and paste the contents of that file from this zip.
   Click **Commit changes**.
3. Open the **Actions** tab. A run called "Build Android APK" starts by itself
   (or click it, then **Run workflow**). Wait about 5-8 minutes for the green tick.
4. Open the finished run, scroll to **Artifacts**, download **health-guide-apk**.
   Unzip it: inside is `app-debug.apk`.
5. Send the APK to your phone and install it (allow "install unknown apps" once).

## Way 2: build on your computer

Install Node.js (LTS) and Android Studio, then in a terminal inside this folder:

    npm install
    npm run setup
    npm run open

In Android Studio wait for Gradle to finish, then Build > Build Bundle(s) / APK(s) > Build APK(s).
To test on your phone: plug it in with USB debugging on and press the green Run button.

## After installing (important for alarms)

- Open the app and tap **Allow** on the notification popup.
- Settings screen > **Allow exact alarms** if the button appears (Android 12+).
- Press **Test alarm** in Settings to hear the ring screen.
- Xiaomi / Oppo / Vivo / Realme / Samsung: in phone Settings > Apps > Health Guide >
  Battery, choose **Unrestricted** and turn on **Autostart**. Without this the phone
  may stop alarms when the app is closed. This is a phone-maker limit, not an app bug.

## Using it as a website instead (no APK)

Upload only the contents of the `www` folder to GitHub Pages or Netlify. It installs from
the browser (Add to Home screen) and works offline. Alarms only ring while it is open,
so use the APK for reliable reminders.
