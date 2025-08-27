Some example URLs with query parameters for cursor-based pagination using Prisma:

**Basic examples:**

```
https://api.example.com/customers?limit=10&cursor=15
```

```
https://api.example.com/customers?limit=5&cursor=100
```

```
https://api.example.com/customers?limit=25&cursor=50
```

**More realistic examples with a full API endpoint:**

```
https://myapp.com/api/v1/customers?limit=10&cursor=1234
```

```
https://localhost:3000/api/customers?limit=20&cursor=5678
```

```
https://api.mycompany.com/users/customers?limit=15&cursor=9999
```

**Query parameter breakdown:**

- `limit=10` - Fetch 10 records (must be between 5-25 as per your validation)
- `cursor=1234` - Start fetching from the record with ID 1234 (auto-increment primary key)

**How this works with Prisma:**
Your server would validate that `limit` is between 5-25, then use Prisma's cursor-based pagination like:

```javascript
const customers = await prisma.customer.findMany({
  take: parseInt(limit), // number of records to fetch
  skip: 1, // skip the cursor record itself
  cursor: {
    id: parseInt(cursor), // the auto-increment ID
  },
  orderBy: {
    id: "asc",
  },
});
```

The cursor represents the last record ID from the previous page, so the next batch starts after that record.
