| Normal Form | Requirements                               |
| ----------- | ------------------------------------------ |
| 1NF         | Atomic values only                         |
| 2NF         | 1NF + No partial dependencies              |
| 3NF         | 2NF + No transitive dependencies           |
| BCNF        | 3NF + Every determinant is a candidate key |

# EER to Relational Model
## 1. Strong Entities
For each regular (strong) entity type E in the ER schema, create a relation R that includes all the simple attributes of E. Include only the simple component attributes of a composite attribute.
## 2. Mapping of Weak Entity Types
self explanatory
## 3. Map 1:1 Relationship types
Identify relations S and T that correspond to the entity types participating in R. We should use the foreign key approach. Choose one of the relations. Let's say S. and include as a foreign key in S, the primary  key of T. It is better to choose an entity type with total participation in R in the role of S. Include all the simple attributes of the 1:1 relationship type R as attributes of S. We can do the vice versa with T and S. 
## 4. Mapping 1:N relationship types
Identify the relation S that represents the participating entity type at the N-side of the relationship type. Include as a foreign key in S the primary key of the relation T that represents the other entity type participating in R. WE do this because each entity instance on the N-side is related to at most one entity instance on the 1-side of the relationship type. Include any simple attributes (or simple components of composite attributes) of the 1:N relationship type as attributes of S. 
## 5. Binary M:N relationship types
For each binary M:N relationship type R, create a new relation S to represent R. Have two foreign keys and you make life easy.
## 6. Multivalued Attributes
For each multivalued attribute A, create a new relation R. This relation R will include an attribute corresponding to A, plus the primary key attribute K as a foreign key in R. For example, we can make a relation DEPT_LOCATIONS to represent the multivalued attribute LOCATIONS of DEPARTMENT with DEPARTMENT's ID that represents the foreign key of DEPT_LOCATIONS.
## 7. Mapping of N-ary Relationship Types
Make a new relation S to represent R. Include as foreign key attributes in S the primary keys of the relations that represent the participating entity types. Also include any simple attributes of the n-ary relationship type as attributes of S. The primary key of S is usually a combo of all the foreign keys that reference the relations representing the participating entity types. However, if the cardinality constraints on any entity types E participating in R is 1, then the primary key of S should not include the foreign key attribute that references the relation E' corresponding to E
