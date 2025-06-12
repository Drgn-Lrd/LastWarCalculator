# Resistance Level Upgrade Calculator Changelog

---

## Initial Submission (Baseline)

This represents the foundational version of the calculator, providing basic functionality for input and display without advanced features.

* **Foundation:** This version was created by translating existing **PowerShell scripts into a functioning HTML website**, providing a graphical user interface for the calculator.
* **Core Functionality:**
    * Basic HTML structure for input fields (levels and resources).
    * Basic JavaScript functions for calculating resource production rate and displaying a time to completion.
    * Minimal CSS for layout and styling.

---

## Version 4.0.0: Core Functionality & Initial Usability Improvements

This version introduced the foundational calculation logic and initial improvements to user input and display.

* **Core Calculation Enhancements:**
    * Implemented precise calculations for "Quartz/hr," "Total Quartz," "Time to Complete," and "Completion Time" based on user inputs.
    * Support for up to 5 Optoelectronic Lab/Workshop levels for rate calculation.
* **Initial Input Handling & Formatting:**
    * Basic formatting of numerical inputs and displays to include **thousands separators** (e.g., `1,000,000`) for improved readability.
    * Application of a **maximum allowed resource value** (`99,999,999,999`) to prevent erroneous large inputs.
* **Basic Time Zone Support:**
    * Introduced initial functionality for displaying completion time, defaulting to the user's local time zone.
* **Basic Styling & Structure:**
    * Enhanced CSS for general layout and appearance.
    * Established the `div.version-info` for displaying version information.

---

## Version 4.1.0: Internationalization & Enhanced Input

This version focused on making the calculator accessible to a wider audience through multi-language support and further refined input handling.

* **Internationalization (i18n) Integration:**
    * **Multi-Language Support:** Full translation capabilities introduced for English, Spanish, Portuguese, Korean, and Japanese.
    * **Dynamic Text Replacement:** Implemented dynamic constant replacement for building names (`Optoelectronic Lab`), resource names (`Quartz`), and building types (`Workshop`) throughout the UI, ensuring consistent terminology across translations.
    * **Language Selector:** Added a dropdown to allow users to manually select their preferred language, with automatic detection of the browser's default language.
* **Advanced Input Handling:**
    * **Resource Decimal Expansion:** Introduced automatic expansion for resource inputs (e.g., `6.8` converts to `6800`, `102.` to `102000`), streamlining data entry, especially for fractional values.
    * Improved `formatInput` to handle both integer and decimal displays appropriately.

---

## Version 4.1.6: Refined User Experience & Accessibility

This version built upon previous improvements, adding intelligent features and ensuring robust display and accessibility across devices.

* **Intelligent Auto-Population:**
    * Added intelligent auto-population of "Quartz Held" fields for buildings that share the same level, significantly reducing repetitive data entry for users with similar structures.
* **Robust Time Zone Management:**
    * **Curated Timezone List:** Provided a refined and sorted list of common time zones.
    * **Accurate Offset Display:** Enhanced calculation and display of UTC offsets for selected time zones, including handling of fractional hour offsets.
    * **Local Timezone Matching:** Improved logic for automatically detecting and suggesting the user's local time zone or the closest available match from the curated list.
* **User Interface & Accessibility:**
    * **Responsive Design:** Comprehensive media queries (`@media (max-width: 480px)`) were implemented to ensure optimal viewing and usability on mobile devices, adjusting layout, spacing, typography, and input sizing for a seamless experience.
    * **Layout Refinements:** Utilized CSS Grid and Flexbox for precise control over element alignment and spacing, particularly for the building input rows, ensuring a cleaner and more organized interface.
    * **Accessibility Improvements:** Enhanced `tabindex` attributes for more logical keyboard navigation, and `aria-labelledby` attributes for improved screen reader support, making the application more usable for everyone.
* **Version Tracking Refinement:**
    * The `div.version-info` was updated to specifically reflect this version and its exact timestamp (`Version 4.1.6 - Last Updated: June 12, 2025, 05:11 AM EDT`).
    * **JavaScript Version Comment:** Added a duplicate of the visible version info (`Version 4.1.6 - Last Updated: June 12, 2025, 05:11 AM EDT`) as a JavaScript comment just before the closing `</script>` tag, improving developer traceability.

---

## Version 4.2.0: Night Mode & Persistent Theme Preference

This version introduces a highly requested visual enhancement, offering a more personalized and comfortable user experience.

* **Night Mode (Dark/Light Theme) Implementation:**
    * **Automatic Theme Detection:** The calculator now automatically applies a dark or light theme based on the user's operating system or browser `prefers-color-scheme` setting upon page load.
    * **Manual Theme Toggle:** Added a dedicated "Toggle Theme" button (with translated text) that allows users to manually switch between three modes:
        1.  **Dark Mode:** Forces the dark theme.
        2.  **Light Mode:** Forces the light theme.
        3.  **System Default:** Reverts to following the OS/browser's `prefers-color-scheme` setting.
    * **Persistent User Preference:** User's manual theme selection is now saved in `localStorage`, ensuring their preferred theme persists across browser sessions.
    * **Dynamic Styling with CSS Variables:** Refactored the styling to use CSS custom properties (variables) for colors, allowing for seamless and efficient theme switching by simply changing the `data-theme` attribute on the `<body>` element.
    * **Smooth Transitions:** Implemented CSS transitions for background and text colors, providing a smooth visual fade when switching themes.
