# Melodo App - Deep Link Handler

This repository contains the redirect service for Melodo, allowing seamless sharing of music profiles across platforms.

## Overview

Melodo is a music discovery and sharing app that lets users showcase their vinyl collections, reviews, and curated music lists. This redirect service ensures links shared from the app work properly for both users who have the app installed and those who don't.

## How It Works

When a user shares content from the Melodo app:

1. A universal link is generated: `https://melodoapp.com/link?id={USER_ID}&type=user`
2. When clicked, this page attempts to open the Melodo app using the direct URL scheme: `melodo://user/{USER_ID}`
3. If the app isn't installed, it presents options to download from the App Store or Google Play

## Repository Structure

- `index.html` - The redirect page that handles the deep linking logic
- `manifest.json` - Web App Manifest for Android devices
- `logo.png` - Main app logo
- `icon-192.png` & `icon-512.png` - Icons for Progressive Web App support

## App Configuration

Melodo uses the following configuration:
- **Bundle ID/Package Name**: com.yourdomain.Melodo
- **URL Scheme**: melodo://
- **Associated Domains**: melodo.com, melodo.page.link
- **App Store ID**: 6744846435

## Local Development

To test locally:
1. Clone this repository
2. Start a local server: `npx serve` or `python -m http.server`
3. Navigate to: `http://localhost:8000/link?id=TEST_ID&type=user`

## Implementation Details

This redirect service was designed as a lightweight alternative to Firebase Dynamic Links, maintaining compatibility with WhatsApp and other messaging platforms by using a standard URL format that's automatically detected and made clickable.

## Further Customization

For additional features or custom behavior:
- Modify `index.html` to change the redirect flow
- Update `manifest.json` to adjust the Progressive Web App behavior
- Replace the icons with your own variations of the app logo

## Support

For issues with this redirect service, please open an issue in this repository.
For app-related questions, contact support through the Melodo app.
