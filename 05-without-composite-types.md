# Without Composite Types

- Composite Types is the name of the Prisma feature
- Plan to add support for nested objects to other DBs e.g. Postgres
- MongoDB calls them **embedded documents**

Example:
```json
{
  "_id": someRandomId,
  "name": "Erkal",
  "height": 190,
  "address": {
    "street": "Somestreet",
    "number": 11,
    "city": {
      "name": "Berlin",
      "position": {
        "lat": "52.5",
        "long": "13.4"}
    }
  }
}
```

Before we added support for composite types, the schema would look like this: 

```tsx
model Person {
  id         String @id @default(dbgenerated()) @map("_id") @db.ObjectId
  name       String
  height     Int
  address    Json
}
```

Where the embedded document `address` is just a `json` object without typed properties.

[Next](./06-with-composite-types.md)