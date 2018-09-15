# star-yaml
Non-proprietary YAML format for star schema and snowflake schema

## Goal

- Simple and readable (YAML)
- No dependency on individual table definition (SQL, GraphQL, etc)
- Integration of any table definition
- *ONLY* join keys will be defined as a connnection among tables

```yaml
apiVersion: v1
kind: Star
tables:
- name: User
  metadata:
    root: true
  definition:
    type: SQL
    url: 'postgres://localhost:5432'
    query: 'users'
  links:
  - to: 'Location'
    as: 'location'
    sameAt:
      address: address
- name: Location
  definition:
    type: graphql-opencrud
    url: 'http://localhost:4021'
    query: 'locations'
```

## Examples

There are example YAMLs to represent each chapter star schemas from Data warehouse toolkit by Ralph Kimball, Mergy Ross
