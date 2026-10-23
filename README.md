# SiteLoop

SiteLoop is an offline-first construction materials reuse app. It matches
material requests with surplus stock across sites, helping reduce unnecessary
purchases and waste.

## Deployment

This repository contains a prebuilt static web app in `siteloop-web/`.
Vercel is configured through [`vercel.json`](./vercel.json) to publish that
directory. No build command or environment variables are required.

To deploy with Vercel:

1. Import this GitHub repository into Vercel.
2. Keep the project root at the repository root.
3. Leave the framework preset as **Other** and deploy.

The app uses hash-based routes and includes a service worker for offline
support, so it does not require server-side routing or an API.
