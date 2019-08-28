# sql-cheatsheet

### Change owner of table

#### Syntax

```sql
ALTER TABLE {{table} OWNER TO {{user}};
```

#### Example

```sql
ALTER TABLE public.audits OWNER TO mmuser;
```
