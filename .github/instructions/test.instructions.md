---
applyTo: '**'
description: Enforces test approach for all code changes and how to run tests
---

# Test Instructions

## Purpose
Enforce a test-first development approach where tests are written before implementation code to ensure better design, higher quality, and comprehensive test coverage.

## Rules

### Code Coverage and Quality
- Aim for high test coverage (>90% for business logic)
- Each public method must have corresponding tests
- Test edge cases, error conditions, and boundary values
- Tests must be isolated and independent
- Use descriptive test method names that explain the scenario

### No Implementation Without Tests
- **NEVER** write production code without corresponding tests
- **NEVER** commit code that reduces test coverage
- **NEVER** skip tests for "simple" or "obvious" code

## Best Practices

### Test Structure
- Follow AAA pattern (Arrange, Act, Assert)
- Use meaningful test names: `MethodName_Scenario_ExpectedResult`
- Keep tests simple and focused on single behavior
- Use test categories to organize tests by feature/component

### Test Data
- Use builders or factories for complex test objects
- Prefer explicit test data over random generators
- Use constants for meaningful test values

### Mocking Strategy
- Mock external dependencies and infrastructure
- Don't mock value objects or simple data structures  
- Use Automocker to reduce boilerplate setup code

### Refactoring
- Refactor tests alongside production code
- Remove duplicate test code through helper methods
- Keep test code as clean as production code

### Implementation Code
- **NEVER** put test code in the implementation. Instead change the behavior of the code to make it more testable.

## Enforcement

### Before Any Code Changes
- **Confidence Check**: Display confidence percentage (must be >97%)
- **Test Verification**: Confirm tests exist and fail appropriately
- **Implementation Plan**: Describe minimal code needed to pass tests

### During Development  
- Run tests frequently during development
- Commit tests and implementation together
- Never commit failing tests to main branch

### Code Review Requirements
- All PRs must include tests for new functionality
- Test coverage reports must show no decrease
- Tests must demonstrate the feature works as intended

## Integration with Follow-up Questions
Before implementing any feature:
1. Ask clarifying questions until confidence >97%
2. Propose test scenarios to verify understanding
3. Get approval on test approach before writing tests
4. Write failing tests first, then minimal implementation

