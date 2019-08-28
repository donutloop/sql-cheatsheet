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

### Create table on database

#### Syntax

```sql
CREATE TABLE public.{{tablename}} (
    {{name}} {{datatype}} {{constrain}},
    ......
);
```

#### Example

```sql

CREATE TABLE public.channelmembers (
    channelid character varying(26) NOT NULL,
    userid character varying(26) NOT NULL,
    roles character varying(64),
    lastviewedat bigint,
    msgcount bigint,
    mentioncount bigint,
    notifyprops character varying(2000),
    lastupdateat bigint,
    schemeuser boolean,
    schemeadmin boolean
);

```
