# Example for nuxt3 with lucky canvas

Specified vue3 as peerDenpendencies.

```json
{
  "name": "nuxt-app",
  "private": true,
  "scripts": {
    "build": "nuxt build",
    "dev": "nuxt dev",
    "generate": "nuxt generate",
    "preview": "nuxt preview",
    "postinstall": "nuxt prepare"
  },
  "devDependencies": {
    "@nuxt/devtools": "latest",
    "@types/node": "^18.17.1",
    "nuxt": "^3.6.5"
  },
  "dependencies": {
    "@lucky-canvas/vue": "^0.1.11"
  },
  "peerDependencies": {
    "vue": "^3.3.4"
  }
}
```
