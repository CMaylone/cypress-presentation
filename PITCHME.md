---

# Cypress.IO
Integration Testing

---

## What you will learn

1. Why run integration tests
2. Comparision to other frameworks
3. Getting up and running

---

## First test

```
describe('My First Test', function() {
  it('Does not do much!', function() {
    expect(true).to.equal(true)
  })
})
```

---
## Writing tests

At a high level the integration tests should:
1. Set up the application state.
2. Take an action.
3. Make an assertion about the resulting application state.





