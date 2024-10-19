# Electron Vite Quick Start

This repository contains a minimal Electron application built using the Vite project and initialized with Electron Forge. It serves as a streamlined starting point for developing Electron applications with modern tooling.

## Key Modifications

To ensure optimal functionality, the following adjustments were made to the standard template:

1. Configuration file conversion:

- Changed `forge.config.ts` to `forge.config.js`
- Updated package.json to include `"type": "module"`
- These changes ensure Vite loads correctly with ES module syntax

2. Dependencies:

- Installed Vite and its associated packages to guarantee proper operation

## SQLite3 Integration

For projects utilizing sqlite3, the vite.main.config.ts file requires modification. Here's the recommended configuration:

```ts
import { defineConfig } from "vite";
import { builtinModules } from "module";

export default defineConfig({
  build: {
    rollupOptions: {
      external: ["sqlite3", ...builtinModules],
    },
    commonjsOptions: {
      ignoreDynamicRequires: true,
    },
  },
});
```

This configuration ensures that sqlite3 and Node.js built-in modules are treated as external dependencies, preventing potential conflicts during the build process.

## Best Practices

- Regularly update dependencies to benefit from the latest features and security patches
- Follow Electron's security best practices when developing your application
- Utilize TypeScript for improved type safety and developer experience
- Implement proper error handling and logging mechanisms

For more detailed information on setup and configuration, please refer to the Electron Forge Vite documentation.
