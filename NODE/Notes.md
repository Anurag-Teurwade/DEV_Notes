
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white) 

## 1. Introduction to Node.js
- **What is Node.js?**  
  - JavaScript runtime built on Chrome's V8 engine.
  - Uses event-driven, non-blocking I/O model (lightweight and efficient).
- **Key Features**:  
  - Single-threaded but supports concurrency via callbacks/async.
  - NPM (Node Package Manager) for libraries/tools.
- **Use Cases**:  
  - APIs (REST, GraphQL), Real-time apps (chat, gaming), Microservices, Scripting.

---

## 2. Setup & Basics
```bash
# Install Node.js (includes npm)
node -v          # Check version
npm init -y      # Initialize a project
````

* **First Script** (`app.js`):

```js
console.log("Hello, Node!"); 
// Run: node app.js
```

---

## 3. Core Modules

### `fs` (File System)

```js
const fs = require('fs');
fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

### `http` (Create Server)

```js
const http = require('http');
http.createServer((req, res) => {
  res.writeHead(200, {'Content-Type': 'text/html'});
  res.end('Hello World!');
}).listen(8080);
```

---

## 4. Modules & NPM

* **Custom Module** (`math.js`):

```js
exports.add = (a, b) => a + b; 
// Import: const math = require('./math');
```

* **NPM Commands**:

```bash
npm install express    # Install package
npm uninstall express  # Remove package
```

---

## 5. Asynchronous Programming

### Callback

```js
function fetchData(callback) {
  setTimeout(() => callback("Data received"), 1000);
}
fetchData((data) => console.log(data));
```

### Promise

```js
fetchData().then(data => console.log(data)).catch(err => console.log(err));
```

### Async/Await

```js
async function getData() {
  const data = await fetchData();
  console.log(data);
}
```

---

## 6. Event-Driven Architecture

* EventEmitter class to create and handle events.

```js
const EventEmitter = require('events');
const emitter = new EventEmitter();

emitter.on('message', (msg) => console.log(msg));
emitter.emit('message', 'Hello Event!');
```

---

## 7. Express.js

### Basic Setup

```js
const express = require('express');
const app = express();
app.get('/', (req, res) => res.send('Home Page'));
app.listen(3000);
```

### Middleware

```js
app.use(express.json()); // Parse JSON bodies
```

---

## 8. Databases (MongoDB + Mongoose)

```js
const mongoose = require('mongoose');
mongoose.connect('mongodb://localhost/test', {useNewUrlParser: true});

const User = mongoose.model('User', { name: String });
const user = new User({ name: 'John' });
user.save().then(() => console.log('User saved'));
```

---

## 9. REST APIs

```js
// GET all users
app.get('/users', (req, res) => {
  User.find().then(users => res.json(users));
});

// POST a user
app.post('/users', (req, res) => {
  const user = new User(req.body);
  user.save().then(() => res.status(201).send(user));
});
```

---

## 10. Error Handling

```js
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});
```

---

## 11. Deployment & Process Management

```bash
# Install PM2 (Process Manager)
npm install pm2 -g
pm2 start app.js  # Run app in background
pm2 save          # Save process list
pm2 list          # View running apps
```

---

## 12. Security Best Practices

* Use `helmet` middleware:

  ```js
  const helmet = require('helmet');
  app.use(helmet());
  ```
* Validate inputs with `express-validator`.
* Never hardcode secrets—use `.env` files!

---

## 13. Project Structure Example

```
project/
├── node_modules/
├── controllers/  # Logic for routes
├── models/       # Database models
├── routes/       # API endpoints
├── app.js        # Main entry point
├── package.json
└── .env          # Environment variables
```

---

## 14. WebSockets (Real-time Communication)

* Use `socket.io` for real-time two-way communication.

```js
const http = require('http').createServer();
const io = require('socket.io')(http);

io.on('connection', (socket) => {
  console.log('User connected');
  socket.on('chat message', msg => {
    io.emit('chat message', msg);
  });
});

http.listen(3000);
```

---

## 15. GraphQL APIs

* GraphQL is a query language alternative to REST.
* Use `graphql` and `express-graphql` packages.

```js
const { graphqlHTTP } = require('express-graphql');
const { buildSchema } = require('graphql');

const schema = buildSchema(`
  type Query {
    hello: String
  }
`);

const root = {
  hello: () => 'Hello world!',
};

app.use('/graphql', graphqlHTTP({
  schema: schema,
  rootValue: root,
  graphiql: true,
}));
```

---

## 16. Microservices Architecture

* Break your app into small independent services.
* Each microservice handles one responsibility.
* Use message queues (RabbitMQ, Kafka) or HTTP APIs for communication.
* Benefits: scalability, easier maintenance.

---

## 17. Serverless Functions

* Run code without managing servers.
* Examples: AWS Lambda, Azure Functions.
* Deploy Node.js functions that auto-scale on demand.
* Good for event-driven tasks and lightweight APIs.

---

## 18. TypeScript with Node.js

* TypeScript adds static typing to JavaScript.
* Use `ts-node` to run `.ts` files.
* Helps catch errors early and improves code quality.

```bash
npm install typescript ts-node @types/node --save-dev
```

* Sample TypeScript code:

```ts
function greet(name: string): string {
  return `Hello, ${name}`;
}
console.log(greet('World'));
```

---

## 19. Performance Tuning & Profiling

* Use built-in profiler:

```bash
node --prof app.js
```

* Analyze CPU profiles with `node --inspect`.
* Use tools like `clinic.js` and `0x` for deep profiling.
* Optimize by:

  * Avoid blocking code
  * Use caching
  * Use clustering (see below)

---

## 20. Clustering & Load Balancing

* Use Node.js cluster module to utilize multiple CPU cores.

```js
const cluster = require('cluster');
const http = require('http');
const numCPUs = require('os').cpus().length;

if (cluster.isMaster) {
  for (let i = 0; i < numCPUs; i++) {
    cluster.fork();
  }
} else {
  http.createServer((req, res) => {
    res.end('Hello from worker');
  }).listen(8000);
}
```

* Helps increase app performance by running workers in parallel.

---

## 21. Building CLI Tools with Node.js

* Use `commander` or `yargs` packages.
* Example:

```js
const { program } = require('commander');

program
  .version('1.0.0')
  .option('-n, --name <type>', 'your name')
  .parse(process.argv);

console.log(`Hello, ${program.name || 'User'}`);
```

---

## 22. Useful Tools & Libraries

* `nodemon`: Auto restart server on file changes.
* `dotenv`: Load environment variables.
* `winston`/`morgan`: Logging.
* `express-validator`: Input validation.
* `jsonwebtoken`: JWT authentication.
* `bcrypt`: Password hashing.



