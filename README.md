# Alex G — Local Music Player

A dark, offline-first music player for desktop browsers and Android. It plays audio files you select or drag into the app. Imported audio is stored locally on that device; it is not uploaded to a server.

## Easiest setup if you only have an Android phone

You can use GitHub's cloud build service to build the APK without installing Android Studio on your phone.

1. In your phone browser, sign in to GitHub or create an account at https://github.com.
2. Create a **public** repository named `alex-g-music` (public is simplest for GitHub Pages; don't upload private music files into the repository).
3. Upload the contents of this project ZIP to the repository. Make sure `public`, `package.json`, `capacitor.config.json`, and the `.github` folder are at the repository root. On mobile, you may need to extract the ZIP first using your phone's Files app, then upload the files. If GitHub's mobile upload flow does not show hidden folders, use GitHub's website in your browser's desktop-site mode to add the `.github/workflows` files.
4. Open the repository's **Actions** tab. If asked, enable GitHub Actions.
5. The **Build Android APK** workflow should start after files are pushed to the `main` branch. Wait for it to finish with a green check.
6. Open that workflow run, scroll to **Artifacts**, and download `Alex-G-debug-APK`. Extract the downloaded ZIP on your phone to find `app-debug.apk`.
7. Tap the APK to install it. Android may ask you to allow your browser or Files app to install unknown apps. Only allow this for the file you just built and trust; you can turn the permission back off afterward.

The workflow creates a **debug APK** for personal testing, not a signed release for publishing on Google Play.

## PC and mobile browser version

The **Publish PC and mobile web version** workflow deploys the `public` folder to GitHub Pages. In the repository settings, make sure Pages is configured to use **GitHub Actions** if it is not already. After a successful workflow, the Pages URL appears in the workflow run. Open that URL on your PC or phone. On Android Chrome, use the browser menu and choose **Install app** or **Add to Home screen** if offered.

## Run locally on a computer (optional)

Install Node.js, then run:

```sh
npm install
npm run start
```

## Features
- Import multiple local audio files with the file picker or drag-and-drop on desktop
- Play/pause, previous/next, seeking, volume, shuffle and repeat
- Search, recently added view and favourites
- Responsive dark interface
- Offline-capable web app shell

## Notes and limitations
- Track titles currently come from filenames; embedded ID3 tags and album-art extraction are not implemented yet.
- Audio format support depends on the device/browser. MP3, WAV, M4A/AAC and OGG are commonly supported; FLAC support varies.
- Music is stored in local browser/app storage. Clearing app or browser data may erase imported copies, but does not delete the original files.
- Do not upload copyrighted songs to the public GitHub repository. Import your own audio files directly into the app.
