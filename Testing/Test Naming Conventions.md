# Naming Convention for Tests

There are numerous benefits of writing tests. They help with regression, provide documentation, and facilitate good design. Tests can wreak havoc when they are hard to read and brittle. 


## Test Naming Conventions

Test names (or titles) should be made up of 3 separate sections that are separated by an underscore (\_).  This pattern was suggested by Roy Osherove in his popular book, [The Art of Unit Testing](https://www.artofunittesting.com/), first published in 2006. This approach prioritizes clarity and readability, serving as living documentation for the codebase.

``` markdown
{UnitOfWork}_{StateUnderTest}_{ExpectedBehavior}
```

| **Argument**         | **Description**                                                                                             |
| -------------------- | ----------------------------------------------------------------------------------------------------------- |
| `{UnitOfWork}`       | Unit Of Work — is the name of the item being tested.  In code, this maybe the name of a method or function. |
| `{StateUnderTest}`   | State Under Test — is the scenario under which the item is being tested.                                    |
| `{ExpectedBehavior}` | Expected Behavior — is the expected behavior when the scenario is invoked                                   |

### Basic Rules

1. **Alphanumeric Characters:** Use only alphanumeric characters (a-z, A-Z, 0–9) and underscores characters.
2. **Pascal Case**: All alphabetic characters should be pascal case (or upper camel case).  For example, `HomePage_CompressionOnLoad_GzippedEnabled` or `PurchaseCart_ValidCreditCard_PaymentAccepted`.


## Online Resources

These are additional resource that you can reference to learn more about this topic:

- Daniel Ward, "Naming conventions for tests in C#", May 9, 2024, https://daninacan.com/naming-conventions-for-tests-in-c/.
- Nataliia Syvynska, "How to Choose the Right Name for Unit Tests", May 22, 2023, https://www.softwaretestingmagazine.com/knowledge/how-to-choose-the-right-name-for-unit-tests/.
- Microsoft Learning, "Unit testing best practices for .NET", December 17, 2025, https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices.

