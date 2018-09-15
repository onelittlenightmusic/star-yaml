# Definition of TABLE

## Types

`type` field represents data store type string such as `sql`, `graphql`.

```yaml
tables:
- name: User
  metadata:
    root: true
  definition:
    type: sql
    url: 'postgres://localhost:5432'
    query: 'users'
```

### Detailed types

Detailed types must be declared in a string concatenated with "-" as for api version 1.

```yaml
  definition:
    type: graphql-opencrud
```

More detailed,

```yaml
  definition:
    type: graphql-opencrud-v1
```