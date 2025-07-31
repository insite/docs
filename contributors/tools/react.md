---
description: Documentation for our React UI development work is available here
---

# React

The article assumes that the reader has an understanding of React and JavaScript/Typescript.\
The React app is implemented as SPA (single-page application)

#### The used tools and packages:

1. We use **Visual Studio Code** as an editor for the project: [https://code.visualstudio.com/download](https://code.visualstudio.com/download)\
   I strongly recommend to master shortcut keys, it will improve the quality of life significantly and you will like VSCode more than VS
2. **NodeJS** is used by React compiler and therefore should be installed (the latest LTS version is preferable): [https://nodejs.org/en/download/prebuilt-installer/current](https://nodejs.org/en/download/prebuilt-installer/current)
3. The code is written with **Typescript**.
4. The application was created with **Vite** build tool with the option “**React** + **Typescript**”\
   See details here: [https://vitejs.dev/guide/](https://vitejs.dev/guide/)
5. Routing (i.e. navigation between pages) is managed by the **React Router** package.\
   See details: [https://reactrouter.com/start/data/installation](https://reactrouter.com/start/data/installation)
6. The Bootstrap components are implemented with **React Bootstrap**.\
   See details: [https://react-bootstrap.netlify.app/docs/getting-started/introduction](https://react-bootstrap.netlify.app/docs/getting-started/introduction)
7. Drag and Drop functionality is implemented using DND Kit package: [https://dndkit.com/](https://dndkit.com/)
8. The testing framework is Jest: [https://jestjs.io/](https://jestjs.io/)

#### The project structure:

1. The project is located in [https://github.com/InSite/Code](https://github.com/InSite/Code) repo in the folder **/src/ui/Shift.UI**
2. The folder **/src** contains the React app code:
3. **/src/api** - contains the code to access Shift API (v2) and InSite API (v1)\
   Note: v1 is used only in the local environment
4. **/src/cache** - custom cache implementation
5. **/src/contexts** - context components
6. **/src/components** contains global components which are used on different pages
7. **/src/helpers** - constants and utility functionality used in the project
8. **/src/hooks** - global hooks used across the application
9. **/src/layouts** - for now only AdminHomeLayout, which is based on AdminHome.master from InSite.UI project
10. **/src/models** - contains global interfaces
11. **/src/routes** - contains pages\
    Each page has its own folder, for example, the page /client/admin/home is in the folder /src/routes/admin/home
12. **/src/routes/\_shared** - custom components with business logic used on pages
13. **/src/main.tsx** - is the React entry point

#### How it works:

1. In the development mode the React app starts its own dev server via Vite at the address [**http://localhost:3000**](http://localhost:3000)\
   In the production mode the React app is in the /source/InSite.UI/React subfolder bundled into a single JS file:
2. When you navigate to the page it:\
   \- Requests the information about the website in general (if it is not yet loaded) via Shift API method **/me/context**\
   \- Load data specific to the entity, like loading the information about a specific user\
   \- If the current session is not authenticated (i.e. when API method returns HTTP status 401 or 403) then React app redirects to the login page ([ASP.NET](http://asp.net) WebForms)

#### How to start the React app:

1. Open the console (PowerShell, CMD or VSCode terminal)
2. Navigate to the folder **/src/ui/Shift.UI**
3. Run the command **npm install** to install all packages
4. Run the command **npm run dev** to start the DEV server
5. If you would like to build the production version then run **npm run build**, this will compile and optimize the React app and copy it to **/source/InSite.UI/React** folder
