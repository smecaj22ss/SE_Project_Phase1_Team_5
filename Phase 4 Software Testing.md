# Phase IV – Software Testing  
## Food Waste Reduction Platform

---

# Introduction to Testing

Software testing is the process of evaluating software components to identify defects, bugs, or unexpected behavior before the system is released to users. Testing helps developers verify that the software functions correctly and satisfies the specified requirements.

Testing is important in software development because it improves:

- Reliability
- Correctness
- Security
- Maintainability
- User experience

For the **Food Waste Reduction Platform**, testing is especially important because the system manages user accounts, food listings, notifications, and real-time updates. Any failure in these functionalities may affect platform usability, security, and overall system performance.

---

# Purpose of Testing

The purpose of testing is to detect errors early and ensure that software components behave correctly under both valid and invalid conditions.

Testing helps:

- Verify system functionality
- Prevent unexpected failures
- Improve software quality
- Ensure secure user access
- Validate user input
- Increase system reliability

In this project, testing ensures that users can successfully register, log in, create listings, browse food listings, and receive notifications without errors.

---

# Chosen Component

## Login Function

The selected component for testing is the **Login Function**.

This component is important because it controls user access to the platform. If the login process does not work correctly, users may be unable to access their accounts, while unauthorized users could gain access to the system.

The login function is also critical because it validates:

- Existing user credentials
- Correct passwords
- Empty input fields
- Invalid login attempts

Since authentication directly affects both system security and user experience, the login functionality must be tested carefully.

---

# Preparing Test Cases

The test cases were designed to cover:

- Valid login scenarios
- Invalid login attempts
- Empty field validation
- Boundary and edge cases

These tests help verify that the login component behaves correctly under different conditions.

| Test ID | Scenario | Input | Expected Result |
|----------|----------|----------|----------------|
| TC01 | Valid login | Correct email and password | User logs in successfully |
| TC02 | Wrong password | Correct email, wrong password | Error message displayed |
| TC03 | User does not exist | Unknown email and password | Error message displayed |
| TC04 | Empty email | Empty email, valid password | Validation message displayed |
| TC05 | Empty password | Valid email, empty password | Validation message displayed |
| TC06 | Both fields empty | Empty email and password | Validation message displayed |
| TC07 | Extra spaces | Email/password with extra spaces | Login rejected or spaces handled properly |

---

# Writing Test Code

The following code demonstrates the implementation of the login functionality and its related test cases using **JavaScript**, **Node.js**, and **Jest**.

## Login Function

```javascript
function login(email, password) {
    const validEmail = "user@test.com";
    const validPassword = "pass123";

    if (email === "" || password === "") {
        return "Email and password are required";
    }

    if (email === validEmail && password === validPassword) {
        return "Login successful";
    }

    return "Invalid email or password";
}

module.exports = login;
```

---

## Test Code

```javascript
const login = require('./login');

test("Valid login", () => {
    expect(login("user@test.com", "pass123"))
        .toBe("Login successful");
});

test("Wrong password", () => {
    expect(login("user@test.com", "wrongpass"))
        .toBe("Invalid email or password");
});

test("Unknown user", () => {
    expect(login("unknown@test.com", "pass123"))
        .toBe("Invalid email or password");
});

test("Empty email", () => {
    expect(login("", "pass123"))
        .toBe("Email and password are required");
});

test("Empty password", () => {
    expect(login("user@test.com", ""))
        .toBe("Email and password are required");
});

test("Both fields empty", () => {
    expect(login("", ""))
        .toBe("Email and password are required");
});

test("Extra spaces", () => {
    expect(login(" user@test.com ", "pass123"))
        .toBe("Invalid email or password");
});
```

---

# Running Tests

The tests were executed using the **Jest** testing framework in Node.js.

## Steps to Run Tests

### Install Jest

```bash
npm install jest
```

### Run the Tests

```bash
npm test
```

---

# Execution Results

| Test Case | Result |
|------------|---------|
| TC01 – Valid login | Passed |
| TC02 – Wrong password | Passed |
| TC03 – Unknown user | Passed |
| TC04 – Empty email | Passed |
| TC05 – Empty password | Passed |
| TC06 – Both fields empty | Passed |
| TC07 – Extra spaces | Passed |

All tests passed successfully, confirming that the login component correctly handles valid and invalid scenarios.

---

# Test Coverage

Test coverage measures how much of the application code is tested through automated testing.

The implemented tests cover:

- Successful login functionality
- Invalid credentials
- Empty input validation
- Boundary conditions
- Input formatting issues

These tests verify the most important execution paths and conditions of the login functionality.

Future improvements may include testing:

- Password encryption
- JWT authentication
- Session management
- SQL injection prevention
- Brute-force attack protection
- API security validation

---

# Testing Tools

| Tool | Purpose |
|------|---------|
| Node.js | Runtime environment |
| Jest | JavaScript testing framework |
| GitHub | Version control |
| Visual Studio Code | Development environment |

---

# Execution Summary

The testing process confirmed that the **Login Function** behaves correctly under different scenarios. The component successfully validates user input, prevents invalid access attempts, and handles empty fields properly.

Testing improved:

- System reliability
- Security validation
- Error handling
- User experience

The implemented tests provide a strong foundation for future testing of other modules such as:

- User Registration
- Food Listings
- Notifications
- Password Reset
- Admin Management

---

# Conclusion

Software testing is an essential phase in software engineering because it ensures that applications function correctly, securely, and reliably.

In the **Food Waste Reduction Platform**, the **Login Function** was selected as the primary component for testing because it directly affects user authentication and system security.

The designed test cases covered normal, invalid, and boundary scenarios, and all tests passed successfully. This demonstrates that the login component satisfies the expected system requirements.

Future work may include:

- Integration testing
- UI testing
- Database testing
- Security testing
- Performance testing

to further improve the overall quality and reliability of the platform.
