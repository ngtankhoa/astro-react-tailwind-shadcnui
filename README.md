# Astro + shadcn/ui Sample

This repository provides a code sample demonstrating the integration of **Astro** with **shadcn/ui**.

> **Note:** At the time of writing, `shadcn/ui` does not support Tailwind CSS v4. Therefore, this project uses Tailwind CSS v3. If you require Tailwind CSS v4 support, please refer to the official documentation for any necessary adjustments.

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/ngtankhoa/astro-react-tailwind-shadcnui?title=astro-react-tailwindv3-shadcnui)

## Overview

This project showcases how to integrate:

- **Astro**: A modern framework for building static and dynamic websites.
- **shadcn/ui**: A powerful UI component library built with Tailwind CSS.
- **Tailwind CSS v3**: A utility-first CSS framework.

## Detail guide

1. **Install dependencies**  
   Run the following command to add the final v5 version of `@astrojs/tailwind` and the final v3 version of `tailwindcss`:

   ```bash
   pnpm add @astrojs/tailwind@^5 tailwindcss@^3
   ```

2. **Manual Installation**  
   Follow the steps in the **Manual Install** section of the [Tailwind CSS Integration Guide for Astro](https://github.com/withastro/docs/blob/1e7f9af85ddaa3074cbc7f649370be965aed498b/src/content/docs/en/guides/integrations-guide/tailwind.mdx)

   > _(Note: This is the older guide for `@astrojs/tailwind` before it was deprecated.)_

3. **Create global styles**  
   Create a file at `styles/globals.css` with the following content:

   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

4. **Set up the layout**  
   Create or update `src/layouts/Layout.astro` with the following content to import the global styles:

   ```astro
   ---
   import '@/styles/globals.css';
   ---
   ```

5. **Update Astro configuration**  
   In your `astro.config.mjs`, update the configuration to set `applyBaseStyles` to `false`:

   ```js
   export default defineConfig({
     integrations: [
       tailwind({
         applyBaseStyles: false,
       }),
     ],
   })
   ```

6. **Configure TypeScript paths**  
   Update your `tsconfig.json` file to include the following configuration:

   ```json
   {
     "compilerOptions": {
       // ...
       "baseUrl": ".",
       "paths": {
         "@/*": ["./src/*"]
       }
       // ...
     }
   }
   ```
