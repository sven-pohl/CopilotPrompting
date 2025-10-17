---
mode: 'agent'
model: 'Claude Sonnet 4.5'
tools: ['githubRepo', 'search/codebase']
description: 'Generate a new React Sample App with Vite'
---

Your goal is to generate a modern React application using the latest version of React with Vite as the build tool.

## Requirements

1. **React Version**: Use React 18+ with the latest stable version
2. **Build Tool**: Use Vite for fast development and optimized production builds
3. **TypeScript**: Enable TypeScript support for type safety
4. **Project Structure**: Follow modern React best practices
5. **UI Library**: Use [Fluent UI React Components](https://react.fluentui.dev/)
5. **Development Experience**: Configure hot module replacement (HMR) and fast refresh

## Setup Instructions

### Initialize the Project

1. Create a new React + TypeScript project using Vite:
   ```bash
   npm create vite@latest my-react-app -- --template react-ts
   ```

2. Navigate to the project directory:
   ```bash
   cd my-react-app
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

### Project Configuration

1. **vite.config.ts**: Ensure proper Vite configuration with React plugin
2. **tsconfig.json**: Configure TypeScript with strict mode enabled
3. **package.json**: Include modern React scripts (dev, build, preview)

### Modern React Patterns

Use the following modern React patterns:

1. **Functional Components**: Use function components with hooks
2. **Hooks**: Leverage useState, useEffect, useContext, useMemo, useCallback
3. **TypeScript**: Define proper interfaces and types for props and state
4. **CSS Modules or Styled Components**: For component-scoped styling
5. **ESLint + Prettier**: For code quality and formatting

### Development Workflow

1. Start the development server:
   ```bash
   npm run dev
   ```

2. Build for production:
   ```bash
   npm run build
   ```

3. Preview production build:
   ```bash
   npm run preview
   ```

## Best Practices

- Use functional components with TypeScript interfaces
- Implement proper error boundaries
- Follow React 19+ concurrent features
- Use Vite's environment variables (.env files)
- Optimize bundle size with code splitting
- Implement lazy loading for routes/components
- Use React.StrictMode in development
- Configure path aliases in tsconfig.json and vite.config.ts

## Sample App Features

Include the following in the generated application:

1. **Component Structure**: Organized folder structure (components, pages, hooks, utils)
2. **Routing**: React Router v6+ for navigation (if multi-page)
3. **State Management**: Context API or modern state management solution
4. **Styling**: Modern CSS approach (CSS Modules, Tailwind, or styled-components)
5. **API Integration**: Example of data fetching with proper loading/error states
6. **Testing Setup**: Vitest configuration for unit tests

## Deliverables

Generate a complete, production-ready React application that includes:

- Properly configured Vite setup
- TypeScript configuration
- Sample components demonstrating best practices
- Clean, maintainable code structure
- README with setup and development instructions
- All necessary configuration files 