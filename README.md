# Automation tests for GUI and API

**This documentation is describing all the GUI and API automation tests created in Cypress.**

## CONTENT

**1. Tool selection**
**2. The structure of tests**
**3. How to run the tests**

## 1. Tool selection

As there were no constraints for the tool selection, I chose Cypress for covering both GUI and API tests. Cypress is a great tool for creating, executing and debugging automated tests. Test results and logs are provided immediately in a user-friendly interface.

All tests can be run together within the same framework that also facilitates their debugging. Cypress can be used for testing anything that can run in a browser.

## 2. Test design and structure

The tests are divided into two parts. The purpose of the first part is to verify if the new post can be created and deleted successfully through GUI.
The second part is testing the API functionality for GET and POST requests.

The second part also required the external data source to be used to maintain the data-driven concept. This was accomplished by creating a csv file from which data was taken for creating new user objects and sending them via post request.

**TECHNICAL TASK 1**

1. Test case 1 - Check that post can be created
   Goal: To check if the user can create a post.
   Test steps: Create a post. Check the visibility and data for the post.

2. Test case 2 - Check that post can be deleted
   Goal: To check if the user can delete a post. Check that deleted post is not visible anymore.
   Test steps: Find a post based on the article title. Delete a post. Check that deleted post is no longer visible.

**TECHNICAL TASK 2**

1. Test Case 1 - Get Users - Check the total number and last name of the first two users
   Goal: To check specific data within the user list.
   Test steps: Send request to get the user list. Check response status and time. Check the number of users, total number, and last name of the first two users.

2. Test Case 2 - Create a new user - Check response code and time, id and creation year
   Goal: To check if the user can be created.
   Test steps: Fill user data based on the external source for creating a user profile. Send post request. Check response status and time. Check the id generated, and check that the creation year corresponds to the current year.

## 3. How to run the tests

1. Check that yarn, cypress, and typescript are installed on your machine, as well as the browser you plan to use to execute the tests.
   Check versions via running the commands: yarn --version, cypress -v, tsc -v
   If no version is known, install needed components: npm install -g npm, npm install --global yarn, yarn add cypress --save-dev, yarn add -g typescript
2. Pull the current version of the test from the repository.
3. Fill the username and password in cypress.env.json
4. Execute any of the following commands based on which part you would like to execute:
   yarn test:run - run all tests from terminal in headless mode
   yarn test:gui - run only GUI tests from terminal in headless mode
   yarn test:api - run only API tests from terminal in headless mode

In case you want more information or have encountered any problems, please feel free to contact the creator at hostakova.evka@gmail.com.
