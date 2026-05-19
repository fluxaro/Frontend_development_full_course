# Assignment — Config Manager

## What You Are Building

A configuration manager that uses `Object.keys()`, `Object.values()`, `Object.entries()`, and `Object.fromEntries()` to read, transform, and display application settings.

---

## Requirements

Create `config-manager.html` with this starting config:

```javascript
const appConfig = {
  appName: 'DevCourse',
  version: '2.1.0',
  theme: 'dark',
  language: 'en',
  fontSize: 16,
  notifications: true,
  maxRetries: 3,
  apiUrl: 'https://api.devcourse.com',
  debugMode: false,
  cacheTimeout: 300,
};
```

### Part 1 — Config Display

- Use `Object.entries()` to display all settings in a table
- Show: Setting Name | Current Value | Type (using `typeof`)
- Colour-code by type: string=blue, number=green, boolean=orange

### Part 2 — Config Statistics

Use `Object.keys()`, `Object.values()`, and `Object.entries()` to show:
- Total number of settings
- Count of each type (how many strings, numbers, booleans)
- All string values listed
- All number values with their sum and average

### Part 3 — Config Editor

- Click any setting in the table to edit it inline
- Save button updates the config object
- Show a "Changes" log of what was modified

### Part 4 — Config Transformations

Use `Object.fromEntries()` to create:
- A "public config" (omit `apiUrl`, `debugMode`)
- A "string config" (only string values)
- A "number config" (only number values)
- Display each transformed config

### Part 5 — Config Merge

- A "Reset to Defaults" button that uses `Object.assign()` to restore defaults
- A "Apply Preset" dropdown with 3 presets (Light Theme, Dark Theme, Developer Mode)
- Each preset uses spread to merge with the current config

---

## What Good Looks Like

- All Object methods are used correctly
- The editor updates the actual config object
- Transformations produce correct filtered/mapped objects
- Presets merge correctly without losing unrelated settings

---

## Submission

Submit `config-manager.html`.
