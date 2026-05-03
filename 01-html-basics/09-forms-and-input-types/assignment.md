# Assignment — Job Application Form

## What You Are Building

Create an HTML page called `job-application.html` — a complete job application form using at least 8 different input types.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### Form Structure
- `<form>` with `action` and `method` attributes
- At least 3 `<fieldset>` groups with `<legend>` labels
- A submit button and a reset button

### Required Input Types (use at least 8)

- `type="text"` — applicant name
- `type="email"` — email address
- `type="tel"` — phone number
- `type="date"` — available start date
- `type="number"` — years of experience
- `type="url"` — portfolio or LinkedIn URL
- `type="file"` — resume upload (accept PDF only)
- `type="radio"` — employment type (full-time, part-time, contract)
- `type="checkbox"` — skills (at least 5 options)
- `<select>` — position applying for (at least 5 options)
- `<textarea>` — cover letter

### Accessibility Requirements
- Every input must have a `<label>` with a matching `for` attribute
- Related inputs must be grouped in `<fieldset>` with `<legend>`
- Required fields must have the `required` attribute
- Required fields must be marked with an asterisk (*) in the label

### Fieldset Groups
1. Personal Information (name, email, phone, location)
2. Professional Details (position, experience, portfolio, resume)
3. Skills and Availability (skills checkboxes, employment type radio, start date)
4. Cover Letter (textarea)

---

## What Good Looks Like

- The form is complete and all inputs have proper labels
- All required fields have `required` attribute
- The file input only accepts PDF files
- Radio buttons for employment type all share the same `name`
- The form passes W3C validation

---

## Bonus Challenges

- Add `autocomplete` attributes to all relevant fields
- Add `minlength` and `maxlength` to text fields
- Add `min` and `max` to the number and date fields
- Add a `<datalist>` for the position field with suggested options
- Add `accept="application/pdf"` to the file input

---

## Submission

Save as `job-application.html` and submit via GitHub.
