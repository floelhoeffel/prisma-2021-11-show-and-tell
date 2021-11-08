# Deprecating type

- Undocumented and buggy `type` usage to alias strings will be deprecated.

Example:

```tsx
type MyId = String @id @default(dbgenerated(new_uuid()))

model A {
  id MyId
}
  
model B {
  id MyId
}
```

From `3.6.0` we will render a warning:

```bash
warning: Unsupported usage of type to create an alias.

This functionality will be removed with the next major release.
If you have a need for aliases, please comment on this issue:
https://github.com/prisma/prisma/issues/9939

  -->  schema.prisma:11
   | 
10 | 
11 | type TestType = String @default("test")
   | 
```

We will then remove support with Prisma `4.0.0`

[Next](./08-db-push.md)