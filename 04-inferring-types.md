# Inferring types by looking at data

Example of **inconsistent** data types for the field `height`:

- types are inferred by sampling data
- what happens if data is inconsistent?

Example: `height` as `String` and `Int`.

```tsx
// Collection: Person
[{
	"_id": someRandomIdA
	"name": "Anna",
	"height": 180
},
{
	"_id": someRandomIdB
	"name": "Siri",
	"height": 160
}
{
	"_id": someRandomIdC
	"name": "Kim",
	"height": "175"
}]
```

The CLI will render the following warning:

```bash
*** WARNING ***

The following fields had data stored in multiple types. The most common type was chosen. If loading data with a type that does not match the one in the data model, the client will crash. Please see the issue: https://github.com/prisma/prisma/issues/9654

- Model "Person", field: "height", chosen data type: "Int32"
```

The resulting schema would look like:

```tsx
model Person {
  id     String @id @default(dbgenerated()) @map("_id") @db.ObjectId
  /// Multiple data types found: String: 33.3%, Int32: 66.7% out of 3 sampled entries
  height Int
  name   String
}
```

= best effort, clean your data or it can/will go wrong.

[Next](./05-without-composite-types.md)