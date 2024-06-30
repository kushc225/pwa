### BELOW ARE THE STEPS FOR THE PROGRESSIVE REACT APP

npm create vite@latest my-pwa --template react
cd my-pwa
npm install
npm install vite-plugin-pwa


Configure the Plugin: Modify your vite.config.js to include the PWA plugin.

import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
import { VitePWA } from 'vite-plugin-pwa';

export default defineConfig({
  plugins: [
    react(),
    VitePWA({
      manifest: {
        name: 'Vite React PWA',
        short_name: 'VitePWA',
        description: 'A Progressive Web App built with Vite and React',
        theme_color: '#ffffff',
        icons: [
          {
            src: 'icons/pwa-192x192.png',
            sizes: '192x192',
            type: 'image/png',
          },
          {
            src: 'icons/pwa-512x512.png',
            sizes: '512x512',
            type: 'image/png',
          },
          {
            src: 'icons/pwa-512x512.png',
            sizes: '512x512',
            type: 'image/png',
            purpose: 'any maskable',
          },
        ],
      },
      registerType: 'autoUpdate',
      workbox: {
        // Workbox options for caching strategies
      },
    }),
  ],
});



npm run build

npm install -g serve
serve -s dist
