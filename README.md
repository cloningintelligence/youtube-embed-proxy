# YouTube Embed Proxy

A simple HTML proxy page to embed YouTube videos in Android WebView.

## Quick Setup Options

### Option 1: GitHub Pages (Recommended - FREE)

1. Create a new GitHub repository (e.g., `youtube-embed-proxy`)
2. Upload `index.html` to the repository
3. Go to Settings → Pages
4. Select "Deploy from main branch"
5. Your URL will be: `https://YOUR_USERNAME.github.io/youtube-embed-proxy/?v=VIDEO_ID`

### Option 2: Vercel (FREE)

1. Install Vercel CLI: `npm install -g vercel`
2. In this directory, run: `vercel`
3. Follow prompts to deploy
4. Your URL will be: `https://YOUR_PROJECT.vercel.app/?v=VIDEO_ID`

### Option 3: Netlify Drop (FREE)

1. Go to https://app.netlify.com/drop
2. Drag and drop the `youtube-embed-proxy` folder
3. Your URL will be: `https://YOUR_SITE.netlify.app/?v=VIDEO_ID`

## Usage in Android App

Once deployed, update `VideoStudyScreen.kt`:

```kotlin
val embedUrl = "https://YOUR_DOMAIN/?v=$videoId"
webView.loadUrl(embedUrl)
```

For example:
```kotlin
val embedUrl = "https://yourusername.github.io/youtube-embed-proxy/?v=$videoId"
```

## How It Works

- The HTML page accepts a video ID via URL parameter (`?v=VIDEO_ID`)
- It creates an iframe pointing to YouTube's official embed URL
- YouTube allows embedding from real HTTPS domains (not local WebView)
- Your Android WebView loads your hosted page, which displays YouTube

## Testing

Test your deployed URL in a browser first:
```
https://YOUR_DOMAIN/?v=W6rb-0AghZE
```

You should see the YouTube video playing.
