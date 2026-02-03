# (Draft) Software Testing: The Testing Pyramid

A common set of best practices and fundamental principles applies across most testing scenarios. Every piece of software has unique aspects.  The strategy for how best practices and principles are implemented will be tailored for each situation. 

A pyramid illustration can be used to demonstrate how the different types of tests fit together.  It is recommended to implement multiple types of tests and find a balance of automated tests for your [continuous-integration](continuous-integration.md) (CI) pipeline. 

![Testing Pyramid](diagram-testing-pyramid.png)


## Unit Tests

These types of tests are at the base of the pyramid.  They should be automated and are responsible for testing an individual piece of code.  The goal of a unit test is to validation of specific components, algorithms, or functions within the code.  They should be implemented in the same programming language as the code it is testing.  These tests are typically written by the developer of the component. Complex tests should not be implemented as unit tests.  

The scope of unit tests are limited to the code.  For speed of execution purposes, the code being unit tested is not allowed to call external resources (databases, servers, etc.).  The application code should be configured to use mocks/stubs for dependencies.

## Integration Tests

These test the integrations between many units of code.  Integration tests should use real dependencies (databases, services). They need to test network setting as one of the integrations they validate.  They need to make sure that credentials to dependencies are valid.  The goal of integration tests is to find issues with interfaces and data flow between components.

The scope of integration tests are limited to your applications code and the dependencies that your application calls. Integration tests do not include a graphic user interface (GUI), not do they include testing user interactions with your application.

These focus on how the different units and modules within your code *work together*.

## Acceptance Tests

An acceptance test ensures that your software works the way a user/customer expects the application to work.  Acceptance tests validate required business functionality and emulate real-world usage conditions on behalf of the paying user or a large customer.

These tests often use automated testing tools, such as Selenium, Cucumber and Playwright.

The scope of acceptance tests are only limited by environment.  The test environment should avoid using production dependencies (databases, services).  Outside of that, acceptance tests should ensure any user/customer interaction with your application works as intended.