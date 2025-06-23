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

---

## Version 4.2.1: UI Control Repositioning & Mobile Alignment Refinement

This version focuses on enhancing the user interface layout by repositioning key interactive controls and refining their display for improved usability and visual balance across all devices.

* **UI Control Relocation:**
    * The Language Selector dropdown and Theme Toggle button have been moved from the top-right of the page to the bottom.
    * **Bottom-Left Alignment:** The Theme Toggle button is now justified to the bottom-left of the page.
    * **Bottom-Right Alignment:** The Language Selector is now justified to the bottom-right of the page.
    * These controls are positioned strategically below the main calculator content but above the version number, providing a consistent and intuitive placement for global settings.
* **Mobile Alignment Refinement:**
    * Addressed an issue where the theme toggle and language selector would stack vertically on smaller screens.
    * Implemented CSS adjustments to ensure both controls remain on the same horizontal line on mobile devices, maintaining their left and right justification for a polished and consistent appearance across all screen sizes.
---

## Version 4.2.2: Enhanced Usability with Instructions and UI Refinements

This version introduces significant improvements to user guidance and interface layout, making the calculator more intuitive and user-friendly.

* **New Instructions Feature:**

  * A "❓" (Instructions) button has been added to the bottom control area.

  * Clicking this button now correctly opens a **pop-up modal window** that provides clear, step-by-step directions on how to use the calculator effectively. The modal now consistently starts hidden and only appears when activated.

  * The instructions are fully localized to match the selected language.

* **Refined Auto-Fill Logic Clarity:**

  * The instructions now explicitly clarify that the **auto-fill feature for "Held" resources only applies to empty fields** when matching workshop levels.

  * Users are informed that they **retain the ability to manually edit** any "Held" resource field, even after auto-fill, to account for unique resource amounts.

* **UI Control Repositioning & Mobile Alignment:**

  * The Theme Toggle button, Instructions button, and Language Selector dropdown have been relocated to the bottom of the page for better accessibility.

  * These controls are now consistently aligned: the Theme Toggle on the **bottom-left**, the Language Selector on the **bottom-right**, and the new Instructions button placed **between them**, providing a balanced and intuitive layout.

  * CSS adjustments ensure these controls remain on a single horizontal line across various mobile screen sizes, preventing unwanted stacking.

* **Terminology Update:**

  * The label "Quartz Needed" has been updated to "**Required Quartz**" for improved clarity and precision in English and its localized equivalents.

---

## Version 4.2.3: Critical Time Zone & Error Fixes

This version provides crucial bug fixes related to time zone calculations and display, ensuring accuracy and eliminating console errors.

* **Hawaii Standard Time (HST) Fix:**
    * Completely removed dynamic time zone lookups for `America/Honolulu`.
    * Hardcoded **`UTC-10` offset** and **`HST` abbreviation** for Hawaii Standard Time in completion time displays, resolving console errors and ensuring accurate output.
* **Dynamic Abbreviation Accuracy:**
    * Enhanced `getShortTimeZoneAbbreviation` to correctly display dynamic abbreviations like **`EDT`** (Eastern Daylight Time) and **`EST`** (Eastern Standard Time) based on DST rules for major time zones.
    * Ensured `Etc/UTC` consistently displays **`UTC`** as its abbreviation.
    * Confirmed `Asia/Dubai` (Gulf Standard Time) correctly displays **`GST`**.
    * Improved overall abbreviation logic for consistent and accurate time zone displays.
* **Error Resolution:**
    * Fixed `Value second out of range` console error by correcting `toLocaleString` options in time zone offset calculations.
* **Timestamp Update:**
    * Updated the "Last Updated" timestamp to **`June 13, 2025, 4:14 PM EDT`** to reflect the latest fixes.

---

## Version 4.2.5: Critical Tally Correction & Versioning

This version focuses on correcting an issue with the resource tally display and refining the versioning logic.

* **Tally Counter Correction:**
  * Removed redundant `(Total Quartz/Required Quartz)` display next to "Total Quartz."
  * Introduced a new "Workshop Held Total" line directly below the workshop resource inputs, which now accurately displays the sum of only the resources held within the workshops.
* **Versioning Refinement:**
  * The version number was correctly incremented to `4.2.5` to reflect a bug fix.

---

## Version 4.2.5: Critical Tally Correction & Versioning

This version focuses on correcting an issue with the resource tally display and refining the versioning logic.

* **Tally Counter Correction:**
  * Removed redundant `(Total Quartz/Required Quartz)` display next to "Total Quartz."
  * Introduced a new "Workshop Held Total" line directly below the workshop resource inputs, which now accurately displays the sum of only the resources held within the workshops.
* **Versioning Refinement:**
  * The version number was correctly incremented to `4.2.5` to reflect a bug fix.

---

## Version 4.2.6: Functionality Restoration & Scope Fixes

This version addresses critical errors introduced in the previous update, restoring full functionality to the calculator.

* **Global Function Scope Fix:**
  * Moved all core JavaScript functions (e.g., `expandDecimal`, `updateCalculations`, `formatInput`, `populateTimezones`) out of the `window.onload` block. This ensures these functions are in the global scope and are accessible to HTML attributes (like `onblur`, `onchange`), resolving previous `ReferenceError`s.
  * **Autofill Zero Issue Fix:** Corrected the autofill logic to ensure that only positive, non-zero values are autofilled into empty resource fields, preventing unintended propagation of zero values.
* **Full Functionality Restoration:**
  * Confirmed and restored the correct operation of all features, including the theme toggle, language/timezone dropdowns, all mathematical calculations, and the intelligent autofill logic.
