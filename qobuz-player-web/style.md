# Qobuz Player Design System

This document outlines the design principles, CSS utilities, and component styles used in the Qobuz Player web interface.

## Core Principles

1.  **Modern & App-like:** The interface is designed to feel like a native application, with smooth transitions, persistent navigation, and a focus on content.
2.  **Glassmorphism:** We use backdrop blurs (`backdrop-blur-md`, `bg-black/80`) to create depth and context, especially in sticky headers and navigation bars.
3.  **Scroll-Driven Animations:** Elements like hero images and headers react to scroll position to maximize screen real estate and provide visual continuity.
4.  **Touch-First:** All interactive elements are sized for touch targets (min 44px), and horizontal lists use snap scrolling for easy navigation.

## Typography

-   **Font:** Inter (System UI default).
-   **Headings:** `text-3xl font-bold tracking-tight` for main page titles.
-   **Subheadings:** `text-xl font-bold` for section headers.
-   **Body:** `text-gray-50` for primary text, `text-gray-400` for secondary text.

## Components

### Buttons (`.btn`)

Standardized button styles are defined in `tailwind.css`.

*   `.btn`: Base class for layout (flex, center, rounded, transition).
*   `.btn-primary`: Blue background, white text, shadow. Used for primary actions (Play, Create).
*   `.btn-secondary`: Dark gray background, border, light text. Used for secondary actions (Cancel, More Info).
*   `.btn-ghost`: Transparent background, hover effect. Used for icon-only buttons or subtle actions.
*   `.btn-danger`: Red background. Used for destructive actions.
*   `.btn-icon`: Circular, aspect-square padding for icon-only buttons.
*   `.btn-sm` / `.btn-lg`: Size modifiers.

### Cards

*   **Album/Playlist Cards:** Rounded corners (`rounded-lg`), shadow (`shadow-md`), and hover lift effect (`hover:scale-105`).
*   **Artist Cards:** Circular images (`rounded-full`) for distinct visual hierarchy.

### Navigation

*   **Bottom Nav:** Fixed, backdrop blurred (`backdrop-blur-md`), with active state highlighting (`text-blue-500`).
*   **Segmented Controls:** Pill-shaped, scrollable horizontal list for filtering content.

## Animations

### View Transitions
Powered by the View Transitions API and `htmx`. Pages morph into each other (`hx-swap="morph:innerHTML transition:true"`).

### Scroll-Driven Animations
*   **.animate-hero-scroll**: Applied to hero sections. Fades out and shrinks the hero image as the user scrolls down.
*   **.animate-sticky-header**: Applied to fixed headers. Slides the header down into view as the user scrolls past the hero section.

## CSS Utilities

*   **.no-scrollbar**: Hides scrollbars while preserving scroll functionality.
*   **.scrollbar-thin**: Custom thin scrollbar for desktop.
*   **safe-area-inset**: Handled via `tailwindcss-safe-area` plugin to respect notches and home indicators.
