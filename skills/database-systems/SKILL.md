---
name: database-systems
description: Master relational and NoSQL databases including PostgreSQL, MongoDB, Redis, and DynamoDB. Learn data modeling, optimization, scaling, and best practices for data persistence.
---

# Database Systems

## Quick Start

### PostgreSQL
```sql
-- Create table
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Insert data
INSERT INTO users (name, email) VALUES ('John', 'john@example.com');

-- Query with JOIN
SELECT u.name, p.title
FROM users u
LEFT JOIN posts p ON u.id = p.user_id;
```

### MongoDB
```javascript
const mongo = require('mongodb');

// Connect
const client = new mongo.MongoClient(uri);
const db = client.db('myapp');

// Insert
await db.collection('users').insertOne({
    name: 'John',
    email: 'john@example.com'
});

// Query
const users = await db.collection('users')
    .find({ name: 'John' })
    .toArray();
```

### Redis
```python
import redis

# Connect
r = redis.Redis(host='localhost', port=6379)

# Set & Get
r.set('user:1:name', 'John')
name = r.get('user:1:name')

# Cache pattern
def get_user(user_id):
    cached = r.get(f'user:{user_id}')
    if cached:
        return json.loads(cached)
    user = fetch_from_db(user_id)
    r.setex(f'user:{user_id}', 3600, json.dumps(user))
    return user
```

## Database Comparison

| Aspect | PostgreSQL | MongoDB | Redis | DynamoDB |
|--------|-----------|---------|-------|----------|
| Type | Relational | Document | In-Memory | Key-Value |
| ACID | Full | Multi-doc | Limited | Eventual |
| Schema | Strict | Flexible | N/A | Flexible |
| Best For | Structured | Flexible | Caching | Serverless |
| Scale | Vertical | Horizontal | Horizontal | Horizontal |

## Key Topics

### Relational Databases (PostgreSQL)
- Schema design & normalization
- ACID transactions
- Indexes & query optimization
- JOIN operations
- Window functions
- CTEs (Common Table Expressions)
- JSON & array support
- Full-text search
- Replication & high availability

### Document Databases (MongoDB)
- Document structure design
- Collections & indexes
- Aggregation pipeline
- Transactions (multi-document)
- Schema validation
- Atlas (managed service)
- Sharding strategies
- Backup & restore

### In-Memory Caching (Redis)
- Data structures (strings, hashes, sets, lists)
- Expiration & TTL
- Pub/Sub messaging
- Transactions & Lua scripting
- Persistence options
- Replication & clustering
- Cache invalidation patterns
- Rate limiting & sessions

### Key-Value Databases (DynamoDB)
- Table design & partition keys
- Global Secondary Indexes (GSI)
- Query & scan operations
- Consistent vs eventual reads
- Batch operations
- Streams & triggers
- Auto-scaling
- Cost optimization

### Advanced Topics
- Database replication
- Master-slave architecture
- Sharding strategies
- Read replicas
- Database monitoring
- Backup & disaster recovery
- Migration strategies
- Database scaling

### Performance Optimization
- Index design
- Query analysis (EXPLAIN)
- Denormalization strategies
- Connection pooling
- Batch processing
- Caching layers
- Query optimization
- Statistics & analysis

## Design Patterns

1. **Relational Design**
   - Normalization (1NF, 2NF, 3NF)
   - Entity-relationship modeling
   - Constraint design
   - Key management

2. **Document Design**
   - Embedding vs references
   - Array handling
   - Nested documents
   - Schema versioning

3. **Caching Strategy**
   - Cache-aside pattern
   - Write-through pattern
   - Write-behind pattern
   - Cache invalidation

4. **Scaling**
   - Vertical scaling
   - Horizontal scaling (sharding)
   - Read replicas
   - Database federation

## Best Practices

1. **Data Modeling**
   - Understand your queries first
   - Denormalize for read performance
   - Avoid N+1 problems
   - Plan for growth
   - Document schema

2. **Performance**
   - Index frequently queried fields
   - Monitor slow queries
   - Use EXPLAIN for analysis
   - Batch operations
   - Connection pooling

3. **Reliability**
   - Regular backups
   - Replication setup
   - Failover planning
   - Monitoring & alerting
   - Testing disaster recovery

4. **Security**
   - Principle of least privilege
   - Encryption at rest
   - Encryption in transit
   - Regular updates
   - Audit logging

## Advanced Resources

- PostgreSQL: https://www.postgresql.org
- MongoDB: https://www.mongodb.com
- Redis: https://redis.io
- DynamoDB: https://aws.amazon.com/dynamodb

## Related Skills

- postgresql-advanced - PostgreSQL specific features
- mongodb-design - Document design patterns
- redis-caching - Caching strategies
- database-optimization - Query tuning
- data-modeling - Schema design principles
- scaling-databases - Sharding and replication
