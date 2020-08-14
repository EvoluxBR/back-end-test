# Telecom Carrier, the backend project.

A cloud telecom carrier needs a web application to control the available phone numbers in inventory.

Prepared with ❤️ by [Evolux Sistemas](https://www.evolux.net.br/) team.

### Briefing

The basic user story is:

> As salespeople supervisor, I can fully manage the numbers for sale in a table.

For an engineering perspective, consider this is just a CRUD. 👍

Frontend workmates are providing a GUI for it.
They're skilled engineers and are already working alongside the server side people,
even before any API is done.
They had to mock this RESTful API, of course.

So you're the one in charge of making this RESTful API come true, while your other
colleagues are working in different important features.

Here's the mandatory stack that must play a major role in your implementation:

- Python (any version) with Flask framework (but no Flask-RESTful nor other rapid tool for it);
- SQLAlchemy ORM with PostgreSQL or SQLite;
- Development environment with `docker` and `docker-compose`.

### More technical details

The whole team agreed with a few specs and technical limitations:

- all payloads for requests and responses are JSON;
- there's an agreement of a data schema (so backend format matches with the mocked format on frontend);
- there will be around 800 available numbers for management, consider any pagination technique.

About the schema, here's a [DID `number`](https://www.3cx.com/pbx/did/) entity example for now:

```json
{
  "id": 42,
  "value": "+55 84 91234-4321",
  "monthyPrice": "0.03",
  "setupPrice": "3.40",
  "currency": "U$"
}
```

Friendly hint: keep in mind the
[precision issues of `float` type for money](https://spin.atomicobject.com/2014/08/14/currency-rounding-errors/).

Another hint, as you should have noticed, is that your team is international,
so do your best trying to code in English.
(Or did you think I was just a fancy challenge written in English by Brazilians for no reason?)

### Extra features

Nobody it's expecting it. 💅 But it will be nice to see any of these things:

- automated unit and/or integration tests;
- any authentication and authorization flow;
- an extra Compose `.yml` file for production mode
(like turning off debug mode, and using one of ASGI/WSGI implementations with Nginx etc).

Just don't overengineer it too much. Keep it simple. And don't try to rob product management role!

### Points of interest

It all depends of the level of seniority you're applying to, of course. But our main observations are:

- general computing knowledge;
- your approach to problems;
- how you're architecting the endpoints, database schema and file modules;
- basic developer experience details like:
  - accurate headers and status codes on responses;
  - meaningful error messsages for client side consumption,
  - exceptional internal error logging,
  - how you prevent ridiculous operations like a negative pricing,
  - any sort of documentation, even if it's a basic docstring;
- consistent programming paradigm usage;
- idiomatic pythonic code;
- application of SOLID and design patterns if needed;
- thinking twice before introducing a new dependency; and
- experience with RESTful APIs design.

Consider we'll be using Docker 19 and Docker Compose 1.25+. So we're expecting to just download
your project and simply run `docker-compose up` to make see it working.

We'll need to know how to test your API, of course, for all CRUD operations.
It may be on an exported Postman project, for example.
But if you write `curl` bash scripts, that will be more than enough too.

Also, give us instructions on how to run the dockerized tests, in case you write them.

Be cool and happy coding!
