# Iagon Tech Task - Interactive Navigation Prototype

A modern implementation of the Iagon Figma prototype, showcasing interactive navigation with custom animation transitions. This project demonstrates advanced frontend techniques using the latest technologies and best practices.

## Overview

This project replicates the Iagon design prototype with a focus on:

- **Custom Animation Transitions**: All animations are implemented using custom Svelte transition functions with cubic bezier easing curves
- **Modern Tech Stack**: Built with SvelteKit, TypeScript, and Tailwind CSS for type-safe, scalable development
- **Component Architecture**: Modular, reusable components following best practices for maintainability
- **Smooth Interactions**: Interactive navigation with fluid motion design and spring physics animations

## Key Features

### Custom Transition Functions

- **Spring Physics**: `slideSpringIn` and `slideSpringOut` transitions create natural, bouncy animation effects using `backIn` and `backOut` easing
- **Staggered Animations**: Independent timing for different animation properties (translate, scale) for more complex motion sequences

### Component-Based Design

- **Link Component** (`Link.svelte`): Reusable navigation link with built-in animations and active state management
- **Responsive Layout**: Clean, modular structure that's easy to extend and maintain
- **State Management**: Leverages Svelte 5's rune system with `$state()` and `$derived()` for reactive state handling

### Modern Technologies

- **SvelteKit**: Latest Svelte framework for building fast, optimized web applications
- **Tailwind CSS**: Utility-first CSS for rapid, responsive design
- **Vite**: Lightning-fast development server and build tool

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```sh
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```sh
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.
