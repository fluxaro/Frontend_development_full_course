# Assignment — Contact Book

## What You Are Building

A contact book application that stores contacts as objects and lets users add, view, search, and delete contacts.

---

## Requirements

Create `contact-book.html` with:

### Data Structure

Each contact is an object:
```javascript
{
  id: 1,
  firstName: 'Alex',
  lastName: 'Rivera',
  email: 'alex@example.com',
  phone: '+234 801 234 5678',
  city: 'Lagos',
  tags: ['friend', 'colleague'],
}
```

Start with at least 5 pre-loaded contacts.

### Part 1 — Display Contacts

- Show all contacts as cards
- Each card shows: full name, email, phone, city, tags
- Use dot notation to access properties
- Use template literals to build the card HTML

### Part 2 — Add Contact

A form to add a new contact with all fields. On submit:
- Create a new contact object using shorthand properties
- Add it to the contacts array
- Re-render the list

### Part 3 — Search

- A search input that filters contacts in real time
- Search across: firstName, lastName, email, city
- Use `Object.values()` to search all string properties

### Part 4 — Delete Contact

- A delete button on each card
- Remove the contact from the array
- Re-render the list

### Part 5 — Contact Details Modal

- Clicking a contact card opens a modal
- Modal shows all properties using `Object.entries()` in a table
- Shows the `typeof` each value

---

## What Good Looks Like

- Contacts are stored as proper objects with all required properties
- Search works across multiple fields
- Adding a contact uses shorthand property syntax
- The details modal uses `Object.entries()` to display all properties dynamically

---

## Submission

Submit `contact-book.html`.
