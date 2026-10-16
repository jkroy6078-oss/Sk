# MYRA AI ULTRA — Android starter

Is starter mein edited `www/index.html` shamil hai. Yeh **APK file nahi** hai; Android project generate aur build karne ke liye Node.js, Android Studio aur Android SDK chahiye.

## Build steps

1. Node.js LTS aur Android Studio install karein.
2. Is folder mein terminal kholkar chalayein:

   ```bash
   npm install
   npx cap add android
   npx cap sync android
   npx cap open android
   ```

3. Android Studio mein Gradle sync complete hone dein. Phir **Build > Build Bundle(s) / APK(s) > Build APK(s)** choose karein.
4. Microphone/camera aur voice features ko actual Android device par test karein. Agar Android WebView permission prompt nahi deta, to native permission handling aur `AndroidManifest.xml` settings ko adjust karna hoga.

## Voice mode

MYRA Settings mein `VOICE MODE` selector add hua hai:
- `Auto`: Gemini Live available ho to Live; warna ElevenLabs key ho to ElevenLabs; otherwise browser voice.
- `Gemini Live`: realtime voice mode.
- `ElevenLabs`: ElevenLabs TTS, browser fallback if unavailable.
- `Browser`: device/browser built-in speech.

## Security warning — zaroor padhein

Abhi HTML Gemini/Claude/ElevenLabs API keys ko browser-side code se direct services par bhejta hai aur `localStorage` mein save karta hai. Yeh production ke liye secure nahi hai: app package ya device access ke through keys expose ho sakti hain. Public distribution se pehle authenticated backend/proxy banayein, provider keys server-side rakhein, usage limits lagayein, aur exposed keys ko rotate karein. Is starter mein backend shamil nahi hai.

## Test status

- Inline JavaScript syntax: `node --check` passed.
- HTML parser check: passed; duplicate static IDs nahi mile.
- Browser runtime/API calls, Android microphone/camera permissions, backend, aur APK build: **abhi verify nahi hue**.
