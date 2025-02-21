# Vue 3 + Vite

1. after cloning the repo open the terminal from VSC and type:

`npm create vite@latest . -- --template vue`

2. to view always from the terminal:

`npm i && npm run dev`

3. delete the style.css file

4. edit the main.js file:

FROM import `'./style.css'` TO import `'./assets/scss/app.scss'`

5. in the 'src' folder --> create 'assets' folder --> create file app.scss 

6. Install the SASS package from the terminal:

`npm add -D sass`

7. install Bootstrap:

`npm i bootstrap @popperjs/core`

> [!TIP]
> (@popperjs/core these are two libraries that allow you to use Bootstrap 100%)

8. install vue-router:

`npm install vue-router@4`

9. create folder 'views' --> create file 'HomeView.vue'

10. modify file 'main.js':

```js

import { createApp } from 'vue'
import './assets/scss/app.scss'
import App from './App.vue'

import router from "./router/index.js"

const app = createApp(App)
app.use(router)

app.mount('#app')

```

11. create folder 'router' --> create file 'index.js':

```js

import { createRouter, createWebHistory } from "vue-router";

import home from "../views/HomeView.vue"

/* ------------------------------------------------- */

const router = createRouter({
    history: createWebHistory(import.meta.env.BASE_URL),
    routes: [
        {
            path: "/",
            name: "home",
            component: home
        }
    ]
})

export default router

```