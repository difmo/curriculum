# Comparing Testing Frameworks

**Prerequisites**

Here are topics that should be understood before this topic:

- HTML/CSS/JavaScript syntax
- Test Driven Development (TDD)
- Node.js


**Objectives**

**Participants will be able to:**

- Differentiate between testing frameworks (e.g., RTL, Jest, Vitest, Supertest, etc.)
- Understand the various use cases for each testing framework

**Specific Things To Learn**

  - What is the difference between unit and integration testing?
  - What makes up a test suite?

**Motivation**

Learning testing frameworks is crucial for improving code quality, speeding up development, and ensuring software reliability. Here's why:

- Enhanced Code Quality: Testing frameworks help catch bugs early, making your code more reliable and less prone to errors.

- Faster Development: Frameworks like Jest and Vitest provide fast feedback, reducing time spent debugging and speeding up the development cycle.

- Better Collaboration: Tests act as documentation, making it easier for teams to collaborate and understand the code.

- Adaptability: Knowing various frameworks like React Testing Library, Mocha, and Supertest prepares you for different projects, whether it’s frontend or backend.

- Improved Debugging: Writing tests improves your ability to identify and fix issues quickly, leading to better problem-solving skills.

### Lesson ###

**What are the differences between unit and integration testing?**
- Unit testing focuses on testing individual units or components of the application in isolation. A "unit" is the smallest testable part of the application, such as a function, method, or class.
  - Used to ensure that each component or function performs as expected on its own.
  - Unit tests are usually written to test a specific feature or logic, verifying that it behaves correctly under various conditions.
- Integration testing focuses on verifying the interactions between multiple units or components to ensure they work together as expected. This could involve testing how functions, modules, or systems collaborate.
  - Used to ensure that integrated components or services work well together.
  - It checks if different parts of the system (like APIs, databases, and external services) are correctly interacting.

**What is a test suite, and what do they consist of?**

A test suite is a group of related tests. Instead of writing one test at a time, you organize them into a collection, called a test suite. Some important aspects of a test suite include:
- Test Suite:
The `describe` block is the test suite. It groups all the tests related to the "Addition function" together.
- Test Case:
Each individual test is written using `test()`. These are the actual tests that check the logic of your code.
- Assertions:
Inside each test, you have assertions (like `expect(add(1, 1)).toBe(2))`, which check if the output of your function matches what you expect.
- Setup: the code that prepares things for the test to run. It could be creating mock data or initializing values before the test starts.
- Teardown: also called cleanup, which happens after a test runs. This could involve resetting values, closing files, or removing data to make sure the next test runs in a clean environment.


Example of a test suite:
```
// Test suite
describe('Addition tests', () => {

// Setup: prepare data before tests
  let num1, num2;
  beforeEach(() => {
    num1 = 1;
    num2 = 1;
  });

// Test case 1: Check if addition works
  test('adds 1 + 1 to equal 2', () => {
    expect(add(num1, num2)).toBe(2);  // Assertion
  });

// Test case 2: Check if addition works with different values
  test('adds 2 + 3 to equal 5', () => {
    expect(add(2, 3)).toBe(5);  // Assertion
  });

// Teardown: Cleanup after tests
  afterEach(() => {
    num1 = num2 = null;  // Cleanup data
  });
});
```

**When to use unit or integration testing?**

Unit Testing:
- Ideal for ensuring that your individual functions, methods, or classes are working correctly.
- Great for validating small pieces of logic early in development.

Integration Testing:
- Crucial when ensuring that multiple components, systems, or services interact properly.
- Important when testing APIs, database connections, or interactions between front-end and back-end systems.

### Testing Frameworks Overview ###
**Jest - [Jest Documentation](https://archive.jestjs.io/docs/en/22.x/getting-started.html)**
- A JavaScript testing framework that is widely used in React and Node.js applications.
- Built-in test runner, assertion library, and mocking capabilities.
- Provides utilities for unit testing, integration testing, and even snapshot testing for UI components.
- Features like watch mode, test coverage, and an easy-to-use API make it one of the most popular choices for developers.

**React Testing Library (RTL) - [RTL Documentation](https://testing-library.com/docs/react-testing-library/intro/)**
- Focuses on testing React components by simulating how users interact with them.
- Provides utility functions like `getBy`, `findBy`, and `queryBy` to query elements based on their visible attributes (e.g., role, text).
- Encourages testing user interactions and component behaviors rather than internal implementation details.
- Works seamlessly with Jest for running tests and assertions.

**Supertest - [Supertest Documentation](https://www.npmjs.com/package/supertest)**
- Designed for testing HTTP APIs by simulating HTTP requests (`GET`, `POST`, `PUT`, `DELETE`) and checking response codes, headers, and body content.
- Ideal for testing RESTful APIs and backend services, often paired with a test runner like Jest or Mocha.
- Makes it easy to write integration tests for server-side code.

**Vitest - [Vitest Documentation](https://vitest.dev/guide/)**
- A modern, fast testing framework for Vite-based projects.
- Optimized for speed with minimal configuration, providing a near-zero-config experience for testing.
- Works natively with ES Modules and offers integrations for frontend and backend testing.
- Suitable for developers looking for a more performance-optimized alternative to Jest, especially in Vite-powered environments.

**Chai & Mocha - [Chai](https://www.chaijs.com/) and [Mocha](https://mochajs.org/) Documentation** 
- Mocha is a test framework that supports asynchronous code, test structuring with `describe` and `it`, and hooks like `before`, `after`.
- Chai is an assertion library that can be used with Mocha (or any test runner), supporting various assertion styles (`expect`, `should`, `assert`).
- Primarily used for general-purpose JavaScript testing across client-side and server-side code.

**Enzyme - [Enzyme Documentation](https://enzymejs.github.io/enzyme/)**
- A React-specific testing utility that offers deep rendering, shallow rendering, and static rendering for testing React components.
- Provides detailed control over component behavior, lifecycle methods, and state.
- Useful for legacy React code, although React Testing Library has become the more modern alternative.

**Jasmine - [Jasmine Documentation](https://jasmine.github.io/pages/getting_started.html)**
- A behavior-driven development (BDD) testing framework designed for testing JavaScript code in isolation, without reliance on a browser or DOM.
- Built-in support for spies, mocks, and stubbing, making it highly flexible for unit testing.
- Suitable for JavaScript applications outside of React, although it can also be used for React testing.

### Best Use Cases ###
- Jest: Ideal for full-fledged JavaScript testing, especially in React and Node.js projects. Its all-in-one nature makes it perfect for unit, integration, and snapshot testing.
- React Testing Library (RTL): Best for testing React components in a way that simulates user behavior and interactions.
- Supertest: Perfect for testing APIs and server-side logic, especially in Node.js applications.
- Vitest: Suited for Vite-based projects where performance and minimal configuration are key priorities.
- Chai & Mocha: Great for unit and integration testing in various JavaScript environments, with flexibility in choosing assertion styles.
- Enzyme: Useful for legacy React code that requires deep component testing.
- Jasmine: Best for behavior-driven development (BDD) and JavaScript unit testing in a non-React environment.

**Independent Practice**

[Rithm School Tutorial - Writing API tests with Jest](https://www.rithmschool.com/courses/intermediate-node-express/api-tests-with-jest)


**Check for Understanding**

1. What is the main purpose of a testing framework?
2. How does knowing different testing frameworks help you in various projects?
3. What is the difference between unit testing and integration testing?

**Supplemental Materials**

- 🎦 [Intro to Jest: Object & API Testing](https://www.dropbox.com/scl/fi/anmkgxuntp8uvlyduzpic/IntroToJestObject-ApiTesting.mp4?rlkey=smzcsizwb1legmhml4xolc72h&dl=0)
- 🎦 [Jest Super Test Integration API Request Testing](https://www.dropbox.com/scl/fi/94h7u58t27zj55teusajo/JestSupertestIntegrationApiRequestTesting.mp4?rlkey=bap50gvtjsmxjt0gasczg3d7a&dl=0) with volunteer Cristina Rodriguez (she/her)

