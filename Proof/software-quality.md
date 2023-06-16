# Software Quality
*You use software tooling and methodology that continuously monitors and improve the software quality during software development.*

## Code Reviews
>Code review (sometimes referred to as peer review) is a software quality assurance activity in which one or several people check a program mainly by viewing and reading parts of its source code, and they do so after implementation or as an interruption of implementation. At least one of the persons must not be the code's author. The persons performing the checking, excluding the author, are called "reviewers".
[Wikipedia on Code review](https://en.wikipedia.org/wiki/Code_review)

In the Group project Code Reviews are used for reasons mentioned above.
In the group project we have a "repository rule" where at least 2 people must have reviewed and approved your code before it can be merged into the developement or main branch.

## Integration Testing
Integration testing is a way to test if the different modules in your application work together as intended. It occurs after unit testing and before system testing.
Integration tests use actual components that the app uses in production, requires more code and data processing and takes longer to run. Therefore if you have behaviour that can be tested with unit tests or integration tests, always choose unit tests. ([ASP.NET introduction to integration tests](https://learn.microsoft.com/en-us/aspnet/core/test/integration-tests?view=aspnetcore-7.0))

### Integration Testing in individual project
In the individual project we have made integration tests, to test the integration between the "Employee-API" and the Frontend.
The integration tests are setup to test the actual endpoints which the frontend calls. To test these endpoints, I have used an application called postman to easily mock the data needed to call the endpoints.

## Important Questions
### What do you consider to be software of high quality?
Software is of high quality when it:
- Serves the purpose it was made for.
- Has no bugs or unintended side affects.
- Is well tested where and when it's needed.
- Is maintainable
- Is readable/understandable (with help of comments)
- Code has documentation where necessary
