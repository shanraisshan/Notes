# MongoDB

> db that is not made by mongols | inspired by the need for a database that could handle large amounts of data, and the word "humongous"


# Python Driver

**PyMongo**
- Type: Synchronous MongoDB driver.
- Use Case: Suitable for blocking/synchronous Python applications.
- Ideal for: Traditional apps (like Flask or scripts) where async support is not needed.

**Motor**
- Type: Asynchronous MongoDB driver built on top of PyMongo using Tornado and asyncio.
- Use Case: Suitable for non-blocking/async Python apps (e.g., FastAPI, Tornado, asyncio-based apps).
- Ideal for: High-performance, concurrent applications using async def and await.
