# GraphQL
garphql

| Term              | Description                                                                | Example                                                               |
|-------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------|
| Schema            | Blueprint of the API, defining types, queries, mutations, subscriptions.    | `type User { id: ID!, name: String }`                                 |
| Query             | Read-only operation to fetch data with a specific structure.                | `query { user(id: "1") { name } }`                                    |
| Mutation          | Operation to modify (create, update, delete) data.                          | `mutation { createUser(name: "John") { id } }`                        |
| Resolver          | Function fetching/modifying data for a field.                               | Resolves `user` by querying a database.                               |
| Type              | Defines data shape (objects, scalars, enums).                               | `type Post { id: ID!, title: String }`                                |
| Field             | Unit of data in a type or query (scalar, object, list).                     | `name` in `type User { name: String }`                                |
| Input Type        | Type for passing complex data to mutations/queries.                         | `input UserInput { name: String }`                                    |
| Subscription      | Real-time operation for data change updates.                                | `subscription { messageAdded { content } }`                           |
| Directive         | Metadata/behavior for schema (e.g., deprecation).                           | `field: String @deprecated`                                           |
| Fragment          | Reusable query piece to avoid field duplication.                            | `fragment UserFields on User { name }`                                |
| Interface         | Abstract type for polymorphic fields.                                       | `interface Node { id: ID! }`                                          |
| Union             | Type representing multiple possible types.                                  | `union SearchResult = User \| Post`                                   |
| Variable          | Placeholder for dynamic query/mutation values.                              | `query ($id: ID!) { user(id: $id) { name } }`                         |
| Introspection     | Querying the schema to discover types and fields.                           | `__schema { types { name } }`                                         |
| Operation Name    | Name for query/mutation/subscription for clarity.                           | `query GetUser { user(id: "1") { name } }`                            |
