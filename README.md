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

### Copy from stdin

#### Syntax

```sql
COPY {{tablename}} ({{column}},{{column}}) FROM stdin;
{{value}} {{value}}
\.
```

#### Example

```sql
COPY public.roles (id, name, displayname, description, createat, updateat, deleteat, permissions, schememanaged, builtin) FROM stdin;
aap88jdt37dgdgkek1c7dq69ua	team_post_all	authentication.roles.team_post_all.name	authentication.roles.team_post_all.description	1552912816230	1552912816230	0	 create_post	f	t
masesduwobn95dqoyba5xmtz5o	team_post_all_public	authentication.roles.team_post_all_public.name	authentication.roles.team_post_all_public.description	1552912816258	1552912816258	0	 create_post_public	f	t
\.
```



### Add primary key constrain to column

#### Syntax

```sql
ALTER TABLE ONLY {{table}}
    ADD CONSTRAINT {{constrain_name}} PRIMARY KEY ({{column}});
```

#### Example

```sql
ALTER TABLE ONLY public.audits
    ADD CONSTRAINT audits_pkey PRIMARY KEY (id);
```

### Add unique constrain to column

#### Syntax

```sql
ALTER TABLE ONLY {{table}}
    ADD CONSTRAINT {{constrain_name}} UNIQUE ({{column}});
```

#### Example

```sql
ALTER TABLE ONLY public.schemes
    ADD CONSTRAINT schemes_name_key UNIQUE (name);
```


