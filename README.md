# PostgreSQL Testing

- **What JavaScript / Node.js tools are available for testing a database?**

Frameworks for testing PostgreSQL:
- [PGtest](https://www.npmjs.com/package/pgtest)
- [PGUnit](http://en.dklab.ru/lib/dklab_pgunit/)
- [PLV8](https://legitimatesounding.com/blog/unit_testing_in_postgresql_with_plv8.html)
- [Sinon.js](http://sinonjs.org/)

The main reason to use Sinon is because of its extensive mock library.

- **Why would you mock a database and how does this help with testing?**

There are three major features to take into consideration: **Spies**, **Stubs** and **Mocks**.
They are all similar in that they provide ways in which to replace a given class's dependencies so that the class can be tested in isolation.

**Spies.**
Test doubles, or spies, get information about function calls and are useful if you want to verify that something happened. You can call spy either as an anonymous function or wrap it in an existing function.

**Stubs.**
Mechanism for injecting data directly into the class.
More versatile than spies and they have additional functionality. They replace the original code, and you never call the function that was originally there.
There are two scenarios in which to use stubs.
1. When you want to control the way code behaves, e.g. to test for error handling.
2. When you have a function with an async call but you don't want to wait for the results to come back.

**Mocks.**
The hardest to use. They're like spies and stubs, but they have expectations that are stated upfront. So when you use these you need to be careful as you might make your tests overly specific and this will make your tests more brittle.

In general, you should only use a max of one mock per test.

![screen shot 2017-03-28 at 16 06 00](https://cloud.githubusercontent.com/assets/16895125/24412504/8abfe3be-13d0-11e7-85f7-a8f575be8b5d.png)

Resources:
- [Advanced Unit Testing Techniques in JavaScript](https://code.tutsplus.com/tutorials/advanced-unit-testing-techniques-in-javascript--net-32892)
- [Mocks, Stubs and Fakes, youtube video](https://www.youtube.com/watch?v=qFaBHHg6RQU)
- [How to use Sinon.JS, a mocking library for testing, youtube video](https://www.youtube.com/watch?v=SvudHPTEsIk&t=321s)
- [Mocking Postgres for unit tests with Sinon.js in Node.js](https://stackoverflow.com/questions/13102693/mocking-postgres-for-unit-tests-with-sinon-js-in-node-js)
- [best way to mock pg (using sinon?) for unit-tests](https://github.com/brianc/node-postgres/issues/1056)
