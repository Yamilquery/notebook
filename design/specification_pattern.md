# Specification Pattern

*From: [Wikipedia](https://en.wikipedia.org/wiki/Specification_pattern)*

> A particular software design pattern, whereby business rules can be recombined by chaining the business rules together using boolean logic. The pattern is frequently used in the context of domain-driven design.

> A specification pattern outlines a business rule that is combinable with other business rules. In this pattern, a unit of business logic inherits its functionality from the abstract aggregate Composite Specification class. The Composite Specification class has one function called IsSatisfiedBy that returns a boolean value. After instantiation, the specification is "chained" with other specifications, making new specifications easily maintainable, yet highly customizable business logic. Furthermore upon instantiation the business logic may, through method invocation or inversion of control, have its state altered in order to become a delegate of other classes such as a persistence repository.

---

## References

-   [Chris Missal: Using the Specification Pattern for QueryingPosted](https://lostechies.com/chrismissal/2009/09/11/using-the-specification-pattern-for-querying)
-   [Culttt: Implementing The Specification Pattern](http://culttt.com/2014/08/25/implementing-specification-pattern)
-   [Martin Fowler: Specifications](http://martinfowler.com/apsupp/spec.pdf)
