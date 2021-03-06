# Indexes and unique constraints

- We decided to not invest into schema migrations as the vast majority* of projects don't use schemas
- added support for `index` and `unique` so at least management of  indexes and constraints is possible,

*over 2/3 of the projects in Atlas don't use schemas

```tsx
model BlogPost {
  id     String @id @map("_id") @db.ObjectId
  author String
  title  String

  @@unique([author, title], map: "titleAuthorShouldBeUniqueUnique")
  @@index([title])
}
```

- adding a unique constraint on the compound of `author` and `title`
- setting and index on `title` for quick lookup of posts by title.

```bash
npx prisma db push
```

Will now push those indexes to the database.

[Back to start](./01-intro.md)


