# Why is MongoDB special?

- **first NoSQL** database @ Prisma
- JSON based documents instead of tables
- schemas optional and rarely used

## Relational DBs

#### Table Person

| id  | name | posts            |
| --- | ---- | ---------------- |
| 1   | Kim  | postId1, postId2 |

#### Table Posts

| id  | title        | content                     |
| --- | ------------ | --------------------------- |
| 1   | Hello World  | This is the best post ever. |
| 2   | Hello Prisma | This is even better.        |

## NoSQL Database

```json

[{
    "id": 1,
    "name: "Kim",
    "posts": [
        {
            "id": 1
            "title": "Hello World"
            "content": "This is the best post ever."
        },
        {
            "id": 2
            "title": "Hello Prisma"
            "content": "This is even better."
        }
    ]
}]

```

[Next](./03-introspection.md)
