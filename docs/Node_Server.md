![Cannastore](./media/graphql_logo.png)

## Node Server

> The reference implementation of the GraphQL specification, designed for running GraphQL in a Node.js environment.

- Sensible defaults & includes everything you need with minimal setup.
- Built-in support for GraphQL subscriptions using WebSockets.
- Works with all GraphQL clients (Apollo, Relay...) and fits seamless in your GraphQL workflow.

### Setup a local GraphQL server

The server can be implented in many ways. Let's make an express server. Why not?

```bash
cd <your-working-directory>
mkdir src && cd src
npm init
npm install express express-graphql graphql
touch index.js
```

__src/index.js__

```javascript
var express = require('express');
var { graphqlHTTP } = require('express-graphql');
var { buildSchema } = require('graphql');
 
var schema = buildSchema(`
  type Query {
    hello: String
  }
`);
 
var root = { hello: () => 'Hello world!' };
 
var app = express();
app.use('/graphql', graphqlHTTP({
  schema: schema,
  rootValue: root,
  graphiql: true,
}));
app.listen(4000, () => console.log('Now browse to localhost:4000/graphql'));
```

### Links

- [graphql.org](https://graphql.org/code/#javascript)
- [GitHub](https://github.com/graphql/graphql-js)
- [NPM](https://www.npmjs.com/package/graphql)

#### Tags/Keywords

Node, ServerThe reference implementation of the GraphQL specification, designed for running GraphQL in a Node.js environment.