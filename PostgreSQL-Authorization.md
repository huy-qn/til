# PostgreSQL-Authorization
- PostgreSQL allows you to **define access control rules** in one place (the db)
- The first layer of any PostgreSQL authorization project is roles. Database roles can represent users and/or groups. A PostgreSQL database will typically start with a single superuser role named "postgres".
- To view the roles that exist in the database, run ```\du```
- ```SELECT current_user, session_user``` to see the role we're using
- The "session_user" is typically going to be the user you connected to the database as (though it can be changed with ```SET SESSION AUTHORIZATION```). The "current_user" is the user you're acting as — it is the user that will be tested against when evaluating privileges and policies. The current_user is changed by using ```SET ROLE and RESET ROLE``` or running ```SECURITY DEFINER```
- Permission to act on database objects is governed by privileges, which are primarily manipulated using ```GRANT``` and ```REVOKE``` commands. We can inspect privileges with the ```\dp``` psql command
-  **Row-Level Security** (RLS)? It’s a way for PostgreSQL to limit what rows of a table are visible to a query. 
- In order to return rows from a table with RLS enabled, we need to write a **policy**.

Sources: 
1. https://www.tangramvision.com/blog/hands-on-with-postgresql-authorization-part-1-roles-and-grants
2. https://www.tangramvision.com/blog/hands-on-with-postgresql-authorization-part-2-row-level-security
