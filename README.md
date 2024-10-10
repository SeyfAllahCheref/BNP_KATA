# The code is inside a zip file called hackerank_CHEREF it is the best I could do since my pc is dead and I had to do the test in work's

# User Authentication

## Environment 

- Angular CLI Version: 15.2.8
- Angular Core Version: 15.2.8
- Default Port: 8000

## Application Demo:

![](https://hrcdn.net/s3_pub/istreet-assets/faD8sSJkdHi5ICdpawb9VA/userAuthentication.gif)

## Functionality Requirements

The module should have the following functionalities:

- The module should have 2 routes -
  - Nav item `Login` should navigate to the default route `/` and loads the `LoginComponent`.
  - Nav item `Profile` should navigate to the route `/profile` which loads the `ProfileComponent`.
  - When a user is logged out, only `Login` nav item should be visible.
  - When a user is logged in, only `Profile` nav item should be visible.

- The app has a service named `AppService` which is used to store the list of user credentials in memory globally. The interface for a `IUser` has been defined in this file having the following structure:

```
  interface IUser {
    fName: string;
    lName: string;
    userName: string;
    password: string;
    phoneNo: string;
    email: string;
    state: string;
  }
```

- In the `LoginComponent` -
  - There are 2 inputs - user name, and password. All are initially empty. 
  - `Submit` button should be disabled until all values are entered. 
  - Clicking on the `Submit` button should navigate to the `ProfileComponent` if the entered credentials are correct.
  - If the credentials are incorrect, clicking on the `Submit` button should show error `Invalid Credentials` in the `<div data-test-id="login-error">`. In this case, reset the input values as well.
  - Reactive forms should not be used. The question expects to handle `Click` event on the `Submit` button.

- In the `ProfileComponent` component -
  - Render the following user details inside `<section data-test-id="profile-card">` : user name, user first name, user last name, user email, user phone number, and user state. 
  - Clicking on the `Logout` button, should logout the user and navigate back to the `LoginComponent`.

- The app has a route guard named `AuthGuard` that does the following:
  - If a user tries to navigate to `/profile` route, without being logged in, it redirects the user to default `/` route.

- For testing purpose, use the username and passwords stored in `AppService`.

## Testing Requirements

The following data-test-id attributes are required in the component for the tests to pass:

- The user name input: `app-input-userName`
- The password input: `app-input-password`
- The login button: `login-button`
- The `div` to show login error: `login-error`
- The `section` to show profile details: `profile-card`
- The logout button: `logout-btn`
- Navigation bar for routing: `app-nav`
- `<a>` for `Login` route: `login-router-link`
- `<a>` for `Profile` route: `profile-router-link`.

## Project Specifications

**Read-only Files**
- src/app/app.component.spec.ts

**Commands**

- run:

```bash
npm start
```

- install:

```bash
npm install
```

- test:

```bash
npm test
```
