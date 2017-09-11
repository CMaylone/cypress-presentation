---

# [Cypress.IO](https://www.cypress.io/)
Integration Testing

---
## What you will learn

1. Why run integration tests
2. Comparision to other frameworks
3. Getting up and running

---
### At a high-level tests should

1. Set up the application state
2. Take an action
3. Make an assertion about the resulting application state

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

* Queryies and interactions can be chained together
```javascript
cy.get('textarea.post-body').type('This is an excellent post.')
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
* Canary
* Chrome
* Chromium
* Electron
* Other browsers are on their roadmap: [more details here](https://github.com/cypress-io/cypress/issues/310)







