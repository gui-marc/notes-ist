__Software Inspections__: analysis of static system representations to discover problems.
__Software Testing__: dynamic verification. Observes the product behavior.

## Continuous Integration (CI)

Basically automated testing. Usually when people open Merge Requests, the code passes through a compilation (or build) process and then it runs some unit and integration tests.

Is particularly important for __large systems__ with many contributors and a complex code-base.

When something fail in the CI process, it sends a message to the developers so that the errors can be fixed.

## Stages of Testing

__Development testing__: system is tested during development to discover bugs and defects.
__Release testing__: A separate testing team test a complete version of the system on deploy.
__User testing__: Users or potential users test the system in their environments.

## Testing Strategies

__Black Box Testing__: test against a specification. Tests are driven by a description that was actually used to produce the software artifact.

__White box testing__: test against an implementation. Tests are driven by the artifact description itself. Usually when the code needs to be ran in a proper way.




