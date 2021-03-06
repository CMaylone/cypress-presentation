---

# [Cypress.IO](https://www.cypress.io/)
Integration Testing

---
## What is Cypress?

* A front end testing tool built for the modern web
* Easy to get up and running
* Tests anything that can run in a browser

---

### Querying

* Use jQuery like syntax to query elements 
```javascript
// Get all label elements with the warning class
cy.get('label.warning')
```
* No need to write a bunch of wait statements. Cypress automatically retries the query until it finds the element or a configured timeout is reached

---

### Interacting

* Queries and interactions can be chained together
```javascript
cy.get('textarea.post-body').type('This is a post.')
```
* When performing interactions Cypress assumes the element is "actionable". For example, when calling a `.click()` command Cypress asserts that the element is:
    * Not being hidden
    * Not being covered
    * Not being disabled
    * Not animating
    
---

### Example

```javascript
describe('Post Resource', function() {
  it('Creating a New Post', function() {
    cy.visit('/posts/new')     // 1.

    cy.get('input.post-title') // 2.
      .type('My First Post')   // 3.

    cy.get('input.post-body')  // 4.
      .type('Hello, world!')   // 5.

    cy.contains('Submit')      // 6.
      .click()                 // 7.

    cy.url()                   // 8.
      .should('include', '/posts/my-first-post')

    cy.get('h1')               // 9.
      .should('contain', 'My First Post')
  })
})
```
@[fragment-range]
@[1]
@[2]
@[3]
@[5]
@[6]
@[5-6]
@[8-9]
@[11-12]
@[14-15]
@[17-18]

---

### Browser Support
* Chrome
* Electron
* Other browsers are on their roadmap: [more details here](https://github.com/cypress-io/cypress/issues/310)

---

### Travis Integration

Easy:

```bash
npm install cypress
cypress run
```

---

### At a high-level tests should

1. Set up the application state
2. Take an action
3. Make an assertion about the resulting application state

---

### Desktop Client

Demo

---








