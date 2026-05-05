An **Index** is a **separate data structure** that improves query speed.

#### Internal Structure
Most databases use a [[09_Core_Abstractions/Algorithms/B-Tree|B-Tree]] index:
- sorted structure
- Allows
	- Binary search
	- Range queries
	- Logarithmic Lookup

#### What actually happens
Without index:

```sql
SELECT * FROM Students WHERE name = "Emiliano";
```

-> Full table scan (check **every** row)

With index: **DB** -> Traverses B-Tree -> Finds matching entries -> Fetches rows

#### Types of Indexes
##### Single-column

```sql
CREATE INDEX idx_name ON Students(name);
```

##### Composite Index

```sql
CREATE INDEX 
```