# FixNow — premium home services starter

A responsive React + Vite web app, with Capacitor configuration for packaging the same app as an Android application.

## Included in this MVP
- Responsive premium customer-facing home page
- Search and service-category filters
- Service details and booking request form
- Local booking history and demo profile (stored in browser/device localStorage)
- How-it-works page
- Capacitor Android wrapper configuration

## Important: current demo limitations
This is a functional front-end MVP. It does **not** yet include a production backend, real OTP authentication, provider accounts/assignment, live tracking, payment processing, or admin moderation. Booking/profile data stays on the current device. Do not collect real customer data or accept payments until a secure backend and privacy policy are added.

## Run as a website
Install Node.js 20+ on a computer:
```bash
npm install
npm run dev
```
Open the local URL shown by Vite. For a production web build:
```bash
npm run build
```
The deployable website is generated in `dist/`. Deploy that folder to a static hosting provider, or connect the repository to a host that builds with `npm run build` and publishes `dist`.

## Build Android APK
Android packaging requires a computer with Node.js 20+, Android Studio, and Android SDK installed.
```bash
npm install
npm run build
npx cap add android
npx cap sync android
npx cap open android
```
In Android Studio, wait for Gradle sync, then use **Build > Build Bundle(s) / APK(s) > Build APK(s)**. For a store release, create a signed release build using **Build > Generate Signed Bundle / APK** and keep the signing key private and backed up.

## Phone-only note
A phone can preview the website and edit files, but the reliable APK build flow requires Android Studio on a supported computer or a configured cloud build service. Do not upload source code containing secrets to public services.

## Before launch
1. Replace demo profile with secure OTP authentication.
2. Add backend database and server-side booking validation.
3. Add provider onboarding, verification, availability, assignment and cancellation flows.
4. Integrate a compliant payment provider only after merchant onboarding.
5. Add privacy policy, terms, support contact, refund/cancellation policy and data deletion process.
6. Test on multiple Android screen sizes and low-network conditions.

## Installable website (PWA)
The project includes a web app manifest, icons and a basic service worker. After deploying over HTTPS, visitors can use their browser's **Add to Home screen / Install app** option. This is a progressive web app install, not an APK and not a substitute for Play Store/Uptodown packaging.

## Deploy from an Android phone (GitHub + Vercel)
1. Create/sign in to GitHub in Chrome.
2. Create a new **public or private repository** named `fixnow`.
3. Extract this ZIP on your phone. In GitHub's repository page, use **Add file → Upload files**. Upload the project files and folders (not the ZIP as a single file), then commit.
4. Sign in to Vercel using GitHub and choose **Add New → Project**. Import `fixnow`.
5. Vercel should detect Vite. Confirm **Build Command** `npm run build` and **Output Directory** `dist`, then Deploy.
6. Vercel provides a public `*.vercel.app` URL. You can later add a custom domain.

If the mobile browser cannot upload folders reliably, use GitHub's mobile app/browser desktop mode or a cloud development environment. Do not share passwords or OTPs with anyone.
