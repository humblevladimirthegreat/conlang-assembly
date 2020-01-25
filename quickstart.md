
1. Download Neo4J from https://neo4j.com/download/  They will ask you for contact information but won't verify it.

2. The desktop client contains a tutorial that you can follow if you wish.

3. Once you've started the database, run the following query:

```
LOAD CSV WITH HEADERS FROM 'https://raw.githubusercontent.com/humblevladimirthegreat/conlang-assembly/master/helloworld.csv' AS row
MERGE (from:Entity {id: row.FromId})
MERGE (relation:Entity {id: row.RelationId})
MERGE (to:Entity {id: row.ToId})
MERGE (from)-[f:FROM]->(relation)
MERGE (relation)-[t:TO]->(to)
RETURN *;
```
