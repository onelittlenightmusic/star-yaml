# star-yaml
Non-proprietary YAML format for star schema and snowflake schema

## Goal

- Simple and readable (YAML)
- No dependency on individual table definition (SQL, GraphQL, etc)
- Integration of any table definition
- *ONLY* join keys will be defined as a connnection among tables

```
apiVersion: v1
kind: Star
schema:
- name: User
  metadata:
    root: true
  definition:
    type: SQL
    url: 'postgres://localhost:5432'
    query: 'users'
  join:
  - label: 'location'
    type: 'Location'
    where:
      address: address
- name: Location
  definition:
    type: GraphQL
    url: 'http://localhost:4021'
    query: 'locations'
```
