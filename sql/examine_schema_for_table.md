`select column_name, data_type from information_schema.columns where table_schema = 'public' AND TABLE_NAME = 'organisations_organisation';`

The above will show a simple table of col name and data type from the table "organisations_organisation" in Postgres;

Replace with:

`select * from information_schema.columns where table_schema = 'public' AND TABLE_NAME = 'organisations_organisation';`

to see all columns.
