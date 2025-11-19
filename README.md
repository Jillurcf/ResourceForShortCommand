# ResourceForShortCommand
- for SHA1 key: ./gradlew signingReport
- Expo reset Project: npx run reset-project
- for .ipa file for ios: eas build -p ios --profile development
- for .apk android : eas build -p android --profile development
- for moving the keStore file to the app: mv ~/my-upload-key.keystore android/app/my-upload-key.keystore
- Open Power Shell in the Mac : echo $SHELL
- Show a list of Simulator: xcrun simctl list devices
- for stripe terminal Announcement: https://groups.google.com/a/lists.stripe.com/g/terminal-announce
- web automation tools: Selenium:
A widely-used open-source framework for automating web browsers. It supports multiple programming languages (Java, Python, C#, etc.) and browsers (Chrome, Firefox, Edge, Safari). Selenium WebDriver is the core component for interacting with browsers, while Selenium IDE offers a record-and-playback feature, and Selenium Grid enables parallel test execution.
Playwright:
Developed by Microsoft, Playwright is a powerful and modern automation framework that enables cross-browser automation (Chromium, Firefox, WebKit). It offers robust features for end-to-end testing, handling modern web features like rich UI interactions, and supports multiple programming languages.
Cypress:
A JavaScript-based end-to-end testing framework specifically designed for modern web applications. It provides unique features like real-time reloading, automatic waiting, and deep debugging capabilities, making it popular for developer-friendly testing.
Puppeteer:
A Node.js library that provides a high-level API for controlling headless Chrome or Chromium browsers. It is commonly used for web scraping, generating PDFs, and automating browser tasks without a visible UI.
Katalon Studio:
An all-in-one automation platform that offers a user-friendly Integrated Development Environment (IDE) for automating web, mobile, and API testing. It combines features for creating, organizing, executing, and reporting on automated tests. 
UiPath:
A leading Robotic Process Automation (RPA) software that includes robust capabilities for web automation. It allows users to automate complex workflows involving web applications, often with a low-code or no-code approach.
## For Deeplinking in wedpress website: /public_html/.well-known/assetlinks.json for android 
-[
  {
    "relation": ["delegate_permission/common.handle_all_urls"],
    "target": {
      "namespace": "android_app",
      "package_name": "com.yourapp",
      "sha256_cert_fingerprints": [
        "YOUR_SHA256_KEY"
      ]
    }
  }
]


## For Deeplinking in wedpress website: /public_html/.well-known/assetlinks.json for ios
- {
  "applinks": {
    "apps": [],
    "details": [
      {
        "appID": "TEAMID.com.yourapp",
        "paths": ["*"]
      }
    ]
  }
}

# after creating .well-known folder we have to upload 
- apple-app-site-association
- assetlinks.json
# For wordpress we have to add these lines: 
 <IfModule mod_headers.c>
 <FilesMatch "(\.json|apple-app-site-association)$">
 Header set Content-Type application/json
 </FilesMatch>
 </IfModule>

 RewriteRule ^\.well-known/ - [L]
 After 
- .htaccess

# for AndroidManifest.xml
- <intent-filter android:autoVerify="true">
    <action android:name="android.intent.action.VIEW"/>
    <category android:name="android.intent.category.DEFAULT"/>
    <category android:name="android.intent.category.BROWSABLE"/>
    <data android:scheme="https"
          android:host="yourdomain.com"/>
</intent-filter>

# For iOS in entitlements 
- applinks: yourdomain.com



