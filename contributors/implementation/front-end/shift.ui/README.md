---
description: Documentation for our React UI development work is available here
---

# React

This guide provides comprehensive documentation for our React UI development workflow and architecture.

## Prerequisites

This documentation assumes familiarity with React and JavaScript/TypeScript fundamentals. Our React application is implemented as a Single Page Application (SPA) using modern development practices and tools.

## Development Stack

### Core Tools

**Visual Studio Code**
- Primary code editor for the project
- Download: [https://code.visualstudio.com/download](https://code.visualstudio.com/download)
- **Tip**: Master keyboard shortcuts to significantly improve development efficiency

**Node.js**
- Required for React compilation and build processes
- Install the latest LTS version: [https://nodejs.org/en/download/prebuilt-installer/current](https://nodejs.org/en/download/prebuilt-installer/current)

### Frontend Technologies

**TypeScript**
- Primary language for type-safe development
- All application code is written in TypeScript

**Vite Build Tool**
- Modern build tool optimized for frontend development
- Project created with "React + TypeScript" template
- Documentation: [https://vitejs.dev/guide/](https://vitejs.dev/guide/)

### Key Libraries

**React Router**
- Handles client-side routing and navigation between pages
- Documentation: [https://reactrouter.com/start/data/installation](https://reactrouter.com/start/data/installation)

**React Bootstrap**
- Bootstrap component implementations for React
- Provides consistent UI components and styling
- Documentation: [https://react-bootstrap.netlify.app/docs/getting-started/introduction](https://react-bootstrap.netlify.app/docs/getting-started/introduction)

**DND Kit**
- Modern drag-and-drop functionality
- Documentation: [https://dndkit.com/](https://dndkit.com/)

**Jest Testing Framework**
- Unit testing and test automation
- Documentation: [https://jestjs.io/](https://jestjs.io/)

## Project Architecture

### Repository Location
- **Repository**: [https://github.com/InSite/Code](https://github.com/InSite/Code)
- **Project Path**: `/src/ui/Shift.UI`

### Directory Structure

The `/src` folder contains the complete React application with the following organization:

```
/src
├── /api              # API integration layer
├── /cache            # Custom caching implementation
├── /contexts         # React context providers
├── /components       # Reusable global components
├── /helpers          # Constants and utility functions
├── /hooks            # Custom React hooks
├── /layouts          # Layout components
├── /models           # TypeScript interfaces and types
├── /routes           # Page components and routing
└── main.tsx          # Application entry point
```

#### Key Directories Explained

**`/src/api`**
- Contains integration code for Shift API (v2) and InSite API (v1)
- Note: v1 API is only used in local development environment

**`/src/cache`**
- Custom cache implementation for optimizing data retrieval and storage

**`/src/contexts`**
- React context components for global state management

**`/src/components`**
- Reusable UI components shared across multiple pages
- Global components that maintain consistency throughout the application

**`/src/helpers`**
- Application constants, configuration values, and utility functions
- Common functionality used across different parts of the application

**`/src/hooks`**
- Custom React hooks that encapsulate reusable stateful logic
- Shared across multiple components for consistent behavior

**`/src/layouts`**
- Layout components that define page structure
- Currently includes `AdminHomeLayout` based on `AdminHome.master` from InSite.UI

**`/src/models`**
- TypeScript interfaces and type definitions
- Ensures type safety across the application

**`/src/routes`**
- Page components organized by route structure
- Each page has its own dedicated folder (e.g., `/client/admin/home` → `/src/routes/admin/home`)

**`/src/routes/_shared`**
- Custom components containing business logic shared between pages
- Reusable page-specific functionality

## Application Flow

### Development Environment
- React development server runs on **http://localhost:3000** via Vite
- Hot module replacement for efficient development workflow

### Production Environment
- Application is bundled into optimized JavaScript files
- Deployed to `/source/InSite.UI/React` subfolder as a single JS bundle

### Page Navigation Process

When navigating to any page, the application follows this sequence:

1. **Context Loading**: Requests general website information via Shift API endpoint `/me/context` (if not already cached)

2. **Entity-Specific Data**: Loads data specific to the current page/entity (e.g., user information, content data)

3. **Authentication Check**: Monitors API responses for authentication status
   - HTTP 401/403 responses trigger automatic redirect to ASP.NET WebForms login page
   - Ensures secure access to authenticated content

## Getting Started

### Initial Setup

1. **Open Terminal**
   - Use PowerShell, Command Prompt, or VSCode integrated terminal

2. **Navigate to Project Directory**
   ```bash
   cd /src/ui/Shift.UI
   ```

3. **Install Dependencies**
   ```bash
   npm install
   ```

### Development Commands

**Start Development Server**
```bash
npm run dev
```
- Launches the development server with hot reload
- Application available at http://localhost:3000

**Build for Production**
```bash
npm run build
```
- Compiles and optimizes the React application
- Outputs production-ready files to `/source/InSite.UI/React` folder
- Creates minified, optimized bundles for deployment

### Development Workflow

1. Start the development server using `npm run dev`
2. Make changes to your code - the server will automatically reload
3. Test your changes in the browser at http://localhost:3000
4. When ready for production, run `npm run build` to create optimized bundles

## Best Practices

- **Type Safety**: Leverage TypeScript for better code quality and developer experience
- **Component Reusability**: Use the `/src/components` directory for shared UI elements
- **Custom Hooks**: Extract reusable logic into custom hooks in `/src/hooks`
- **API Integration**: Keep API calls organized in the `/src/api` directory
- **Testing**: Write tests using Jest to ensure code reliability

## Troubleshooting

If you encounter issues:
1. Ensure Node.js LTS version is installed
2. Clear node_modules and reinstall: `rm -rf node_modules && npm install`
3. Check that all required dependencies are properly installed
4. Verify API endpoints are accessible and authentication is working
