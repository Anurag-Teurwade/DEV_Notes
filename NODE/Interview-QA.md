# 🧪 Node.js Interview Questions & Answers

1. **What is Node.js?**  
   Node.js is a runtime environment that executes JavaScript outside the browser using Google's V8 engine.

2. **What are the key features of Node.js?**  
   Event-driven, non-blocking I/O, single-threaded, highly scalable.

3. **What is the event loop in Node.js?**  
   It handles asynchronous callbacks and allows Node.js to perform non-blocking operations.

4. **How does Node.js handle concurrency?**  
   Through the event loop and asynchronous callbacks, not multi-threading.

5. **What is npm?**  
   Node Package Manager, used to install and manage Node.js packages.

6. **What is the difference between `process.nextTick()` and `setImmediate()`?**  
   `process.nextTick()` executes before the event loop continues; `setImmediate()` executes on the next iteration of the event loop.

7. **Explain the concept of callbacks in Node.js.**  
   Functions passed as arguments to be executed after an async operation completes.

8. **What are Promises?**  
   Objects representing eventual completion or failure of an async operation.

9. **What is Async/Await?**  
   Syntactic sugar over Promises for writing asynchronous code in a synchronous style.

10. **What is the difference between blocking and non-blocking code?**  
    Blocking waits for operation completion; non-blocking moves on without waiting.

11. **What is the `require` function?**  
    Used to import modules in Node.js.

12. **What is a module in Node.js?**  
    A reusable block of code encapsulated in a file.

13. **Explain CommonJS.**  
    Module system used in Node.js with `require` and `module.exports`.

14. **What is the difference between `exports` and `module.exports`?**  
    `module.exports` is the actual exported object; `exports` is a shortcut reference.

15. **What is middleware in Express.js?**  
    Functions executed during the request-response cycle.

16. **What are streams in Node.js?**  
    Objects for reading/writing data piece-by-piece instead of all at once.

17. **Name different types of streams.**  
    Readable, Writable, Duplex, Transform.

18. **What is a Buffer?**  
    Temporary storage for binary data in Node.js.

19. **How do you handle errors in Node.js?**  
    Using error-first callbacks, try/catch in async functions, or event handlers.

20. **What is EventEmitter?**  
    A class for handling events and listeners.

21. **What is the difference between `fs.readFile` and `fs.createReadStream`?**  
    `readFile` reads whole file into memory; `createReadStream` reads in chunks.

22. **How do you create a simple HTTP server in Node.js?**  
    Using `http.createServer()` and listening on a port.

23. **What is the purpose of `package.json`?**  
    Metadata file for the project, dependencies, scripts, and config.

24. **How do you update a package using npm?**  
    `npm update <package-name>`

25. **What is the difference between `npm install` and `npm ci`?**  
    `npm ci` installs from `package-lock.json` with a clean slate, faster for CI/CD.

26. **Explain the concept of callbacks hell and how to avoid it.**  
    Nested callbacks causing unreadable code; use Promises or Async/Await.

27. **What is cluster module?**  
    Allows Node.js to create child processes to handle load across CPU cores.

28. **How do you debug a Node.js application?**  
    Using `node inspect`, Chrome DevTools, or VS Code debugger.

29. **What is Express.js?**  
    A minimal and flexible Node.js web application framework.

30. **How do you handle CORS in Express?**  
    Using the `cors` middleware package.

31. **What are environment variables and how do you manage them in Node.js?**  
    Variables to store config values; managed via `.env` files and `dotenv` package.

32. **How do you secure a Node.js application?**  
    Input validation, HTTPS, Helmet middleware, sanitization, and proper auth.

33. **What is the difference between `process.env` and `dotenv`?**  
    `process.env` accesses env vars; `dotenv` loads them from a file.

34. **What is a REST API?**  
    Architectural style for designing networked applications.

35. **How do you create REST endpoints in Express?**  
    Using app methods like `app.get()`, `app.post()`, `app.put()`, `app.delete()`.

36. **What is middleware chaining?**  
    Passing control from one middleware function to the next using `next()`.

37. **How do you handle file uploads in Node.js?**  
    Using middleware like `multer`.

38. **What is the purpose of `next()` in Express middleware?**  
    To pass control to the next middleware.

39. **How does Node.js handle child processes?**  
    Using the `child_process` module.

40. **What is the difference between `fork()` and `spawn()`?**  
    `fork()` spawns new Node.js process; `spawn()` launches any process.

41. **What is PM2?**  
    A process manager for Node.js apps to keep them running.

42. **How do you connect Node.js with MongoDB?**  
    Using libraries like `mongoose` or `mongodb` driver.

43. **What is event-driven programming?**  
    Programming paradigm based on events and listeners.

44. **What is the difference between synchronous and asynchronous functions?**  
    Sync blocks execution; async runs in background.

45. **How do you manage sessions in Node.js?**  
    Using packages like `express-session`.

46. **What is WebSocket?**  
    Protocol for full-duplex communication between client and server.

47. **How can you optimize Node.js performance?**  
    Clustering, caching, avoiding blocking code, using streams.

48. **What is the difference between `setTimeout()` and `setImmediate()`?**  
    `setTimeout()` schedules after a delay; `setImmediate()` runs immediately after I/O events.

49. **Explain the `process` object in Node.js.**  
    Provides info about and control over the current Node.js process.

50. **How do you handle uncaught exceptions in Node.js?**  
    Using `process.on('uncaughtException')` and proper error handling.
