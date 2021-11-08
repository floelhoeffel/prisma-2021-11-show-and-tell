# Context: Why is MongoDB special?

- **first NoSQL** database @ Prisma
- JSON based documents instead of tables
- usually **untyped**

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

## Relational DBs

#### Table Person

| id [Int] | name [String] |
| -------- | ------------- |
| 1        | Kim           |

#### Table Posts

| id [Int] | title [String] | content [Text]              | personID [Int] |
| -------- | -------------- | --------------------------- | -------------- |
| 1        | Hello World    | This is the best post ever. | 1              |
| 2        | Hello Prisma   | This is even better.        | 1              |

[Next](./03-introspection.md)
