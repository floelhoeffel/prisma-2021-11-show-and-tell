# With Composite Types

- Inferring `type` per each level of nested objects

Introspecting the same collection, now yields a fully typed structure:

```tsx
model Person {
  id      String         @id @default(dbgenerated()) @map("_id") @db.ObjectId
  address PersonAddress
  /// Multiple data types found: String: 33.3%, Int32: 66.7% out of 3 sampled entries
  height  Int
  name    String         @unique
}

type PersonAddress {
  city   PersonAddressCity
  number Int
  street String
}

type PersonAddressCity {
  name     String
  position PersonAddressCityPosition
}

type PersonAddressCityPosition {
  lat  String
  long String
}
```

The depth of introspection can be configured via a new CLI param:

```bash
npx prisma db pull --composite-type-depth=2
```

To skip introspection the depth is set to `0`, to go all the way use `-1`.

[Next](./07-deprecating-type.md)