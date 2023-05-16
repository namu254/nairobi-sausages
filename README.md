# Nairobi Sausages
This project is a user interface (UI) for pig farmers to login and upload details of their animals. Farmers can purchase feeds from Nairobi Sausages and eventually sell the full grown pigs to them. The price will vary according to the age and weight of the pigs.


### Framework
- Vue 3 (using JavaScript) 
### CSS Preprocessor
- SASS
### Build Tool
- Vite 4

### Install Instructions
```bash
git clone https://github.com/namu254/nairobi-sausages.git
cd nairobi-sausages
npm install
npm run serve
```
### Interfaces 
The project contains the following interface:

- Login Screen: [https://nairobi-sausages.vercel.app/login](https://nairobi-sausages.vercel.app/login)
- Dashboard: [https://nairobi-sausages.vercel.app](https://nairobi-sausages.vercel.app)
- Submit Pig Details: [https://nairobi-sausages.vercel.app/sell](https://nairobi-sausages.vercel.app/sell)


### Vite Plugin [`vite-plugin-ssr`](https://vite-plugin-ssr.com/) is used for server-side rendering.

Files and folders to note

- `api/ssr.js`: This Vercel API Route is responsible for server-side rendering when deploying to Vercel hosting
- `pages/`: This folder contains the Vue single-file components (pages) that represent different routes in the application
  - `Index`: The dashboard components
  - `Login`: The Login page
  - `Sell`: Submit pig details page
- `public/`: This folder contains the assets used
- `renderer/PageShell.vue`: This file contains the layout of the app



