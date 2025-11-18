---
name: architecture-security
description: Master system design, software architecture, API design, security practices, code review, and blockchain technology. Design robust systems with enterprise-grade security.
---

# Architecture & Security Mastery

## Quick Start

Choose your specialization:

```
// System Architecture: Scalability, design patterns
// API Design: REST, GraphQL best practices
// Security: Application, network, data security
// Code Quality: Review, testing, clean code
// Blockchain: Distributed systems, smart contracts
```

## System Architecture

### 1. System Design Fundamentals
Design scalable systems:
- **Scalability**: Horizontal vs vertical scaling
- **Load Balancing**: Traffic distribution
- **Caching**: In-memory caching strategies
- **Database Scaling**: Sharding, replication
- **Asynchronous Processing**: Queues and jobs
- **Service Discovery**: Dynamic routing
- **Circuit Breakers**: Fault tolerance

**Key Concepts**:
- CAP Theorem: Consistency, Availability, Partition tolerance
- Eventual Consistency: Distributed data consistency
- Idempotency: Repeated operations safety
- Rate Limiting: Prevent overload
- Graceful Degradation: Partial service availability

### 2. Software Architecture Patterns
Structural design approaches:
- **Monolithic**: Traditional single-unit deployment
- **Microservices**: Independent services architecture
- **Serverless**: Function-based, managed execution
- **Event-Driven**: Asynchronous event processing
- **CQRS**: Separate read and write models
- **Domain-Driven Design**: Business logic centered
- **Layered**: Horizontal separation of concerns

**Decision Factors**:
- Team size and structure
- Scalability requirements
- Operational complexity
- Development velocity
- Cost considerations

### 3. Software Design Patterns
Proven solutions for common problems:
- **Creational**: Singleton, Factory, Builder, Prototype
- **Structural**: Adapter, Decorator, Facade, Proxy, Bridge
- **Behavioral**: Observer, Strategy, Command, State, Iterator
- **Architectural**: MVC, MVP, MVVM, clean architecture

**When to Use Patterns**:
- Don't over-engineer simple problems
- Use patterns to solve actual problems
- Learn pattern trade-offs
- Refactor into patterns as needed

### 4. Database Design
Data modeling and optimization:
- **Relational Design**: Normalization, schemas
- **Indexing**: Query optimization, B-tree structures
- **Query Performance**: Execution plans, profiling
- **Denormalization**: Performance trade-offs
- **Replication**: Data consistency, high availability
- **Partitioning**: Horizontal data scaling
- **NoSQL Design**: Document and key-value models

**Database Types**:
- SQL: PostgreSQL, MySQL, SQL Server
- NoSQL: MongoDB, Cassandra, DynamoDB
- Time-series: InfluxDB, Prometheus
- Search: Elasticsearch, Solr

## API Design

### 1. RESTful API Design
HTTP-based API best practices:
- **REST Constraints**: Stateless, cacheable, uniform interface
- **HTTP Methods**: GET, POST, PUT, PATCH, DELETE
- **Status Codes**: 1xx, 2xx, 3xx, 4xx, 5xx semantics
- **Headers**: Content-Type, Accept, caching headers
- **Versioning**: URL, header, or content negotiation strategies
- **Error Responses**: Consistent error format
- **Rate Limiting**: Prevent abuse and overload

**Best Practices**:
- Use nouns for resources, not verbs
- Use HTTP methods semantically
- Return appropriate status codes
- Implement pagination for large datasets
- Document with OpenAPI/Swagger
- Support filtering and sorting
- Use HAL or HATEOAS for discoverability

### 2. GraphQL API Design
Query language for APIs:
- **Schema Design**: Types, fields, resolver patterns
- **Queries**: Data fetching with flexibility
- **Mutations**: Data modification patterns
- **Subscriptions**: Real-time updates
- **Resolvers**: Field value computation
- **Batching**: N+1 query prevention
- **Error Handling**: Field-level errors

**Advantages**:
- Client specifies exact data needed
- Single endpoint flexibility
- Strongly typed schema
- Excellent developer experience

**Trade-offs**:
- Complexity vs REST simplicity
- Caching challenges
- Query cost calculation

### 3. API Security
Protect your APIs:
- **Authentication**: API keys, JWT, OAuth 2.0
- **Authorization**: Role-based access control (RBAC)
- **Rate Limiting**: Prevent abuse
- **Input Validation**: Prevent injection attacks
- **Output Encoding**: Prevent XSS
- **HTTPS/TLS**: Encrypted communication
- **CORS**: Cross-origin resource sharing

**Security Headers**:
- X-Content-Type-Options: NOSNIFF
- X-Frame-Options: DENY or SAMEORIGIN
- Strict-Transport-Security: HTTPS enforcement
- Content-Security-Policy: XSS protection

## Code Review & Quality

### 1. Code Review Best Practices
Effective code review process:
- **Review Objectives**: Quality, security, maintainability
- **Code Standards**: Consistency, naming conventions
- **Testing Requirements**: Coverage, edge cases
- **Security Vulnerabilities**: OWASP Top 10
- **Performance**: Algorithm efficiency, resource usage
- **Documentation**: Clarity and completeness
- **Feedback Style**: Constructive, collaborative

**Review Checklist**:
- Follows coding standards
- Functions single responsibility
- Test coverage adequate
- Comments clear and necessary
- No hardcoded values
- Error handling present
- Security vulnerabilities absent

### 2. Clean Code Principles
Write maintainable code:
- **Meaningful Names**: Revealing intent
- **Functions**: Small, single purpose
- **Comments**: Explain why, not what
- **Error Handling**: Proper exception handling
- **Formatting**: Consistent style
- **DRY**: Don't Repeat Yourself
- **SOLID Principles**: Design principles

### 3. Testing Strategy
Comprehensive test coverage:
- **Unit Tests**: Individual function testing
- **Integration Tests**: Multiple component interaction
- **End-to-End Tests**: Full user workflow
- **Performance Tests**: Load and stress testing
- **Security Tests**: Vulnerability scanning
- **Test Pyramid**: More unit than integration tests
- **Continuous Testing**: Automated test execution

## Security & Cybersecurity

### 1. Application Security
Secure application development:
- **OWASP Top 10**: Injection, XSS, CSRF, etc.
- **Input Validation**: Prevent malicious input
- **SQL Injection Prevention**: Parameterized queries
- **XSS Prevention**: Output encoding
- **CSRF Prevention**: Token-based protection
- **Authentication**: Secure session management
- **Authorization**: Proper access control

### 2. Network Security
Infrastructure security:
- **Firewalls**: Inbound/outbound rules
- **VPN**: Encrypted tunnels
- **TLS/SSL**: Encrypted communication
- **DDoS Protection**: Attack mitigation
- **Intrusion Detection**: Network monitoring
- **VPC Isolation**: Network segmentation
- **Network Policies**: Zero-trust model

### 3. Data Security
Protect sensitive information:
- **Encryption**: Symmetric and asymmetric
- **Hashing**: Password and data integrity
- **Key Management**: Secure key storage
- **Data Classification**: Categorize sensitivity
- **Access Control**: Least privilege principle
- **Backup & Recovery**: Data protection
- **Privacy**: GDPR, CCPA compliance

### 4. Cryptography Basics
Essential cryptographic concepts:
- **Symmetric**: AES, DES (same key)
- **Asymmetric**: RSA, ECC (public/private keys)
- **Hashing**: SHA-256, bcrypt (one-way)
- **Digital Signatures**: Authentication and non-repudiation
- **Key Exchange**: Diffie-Hellman, ECDH

## Blockchain & Distributed Systems

### 1. Blockchain Fundamentals
Distributed ledger technology:
- **Distributed Ledger**: Decentralized data storage
- **Cryptographic Hashing**: Data integrity
- **Merkle Trees**: Efficient verification
- **Consensus Mechanisms**: PoW, PoS, BFT
- **Smart Contracts**: Automated agreements
- **Cryptocurrencies**: Bitcoin, Ethereum
- **Blockchain Types**: Public, private, hybrid

### 2. Smart Contracts
Blockchain automation:
- **Solidity Language**: Ethereum smart contracts
- **Contract Architecture**: Design patterns
- **Gas Optimization**: Efficient execution
- **Security**: Common vulnerabilities
- **Testing**: Hardhat, Foundry frameworks
- **Deployment**: Network selection, upgradability
- **Audit**: Security assessment

### 3. Distributed System Concepts
Understanding decentralization:
- **Byzantine Fault Tolerance**: Reaching consensus despite faults
- **Consensus Algorithms**: Agreement on state
- **Replication**: Consistency and availability
- **Partition Tolerance**: Network failures
- **Distributed Transactions**: ACID across nodes
- **State Consistency**: Eventual vs strong

## Learning Paths

### Software Architect Path
1. System design fundamentals
2. Design patterns mastery
3. Database design and optimization
4. API design (REST and/or GraphQL)
5. Large-scale system projects

### Security Engineer Path
1. Security fundamentals
2. Network security deep dive
3. Application security mastery
4. Cryptography basics
5. Security architecture design
6. Certification (CEH, OSCP)

### Code Review Expert Path
1. Clean code principles
2. Design patterns
3. Testing strategies
4. Security implications
5. Performance optimization
6. Code review leadership

### Blockchain Developer Path
1. Blockchain fundamentals
2. Smart contract development
3. Distributed systems
4. DApp architecture
5. Security auditing

## Tools & Technologies

### Architecture & Design
- Architecture decision records (ADRs)
- C4 model for diagrams
- Lucidchart, Miro for visualization
- ArchiMate notation

### API Documentation
- OpenAPI/Swagger specification
- Postman, Insomnia for testing
- API Blueprint for design
- Stoplight for visual design

### Code Quality
- SonarQube for code analysis
- ESLint, Prettier for JavaScript
- Checkstyle for Java
- pylint for Python

### Security Tools
- OWASP ZAP for penetration testing
- Burp Suite for security testing
- Snyk for vulnerability scanning
- HashiCorp Vault for secrets
- TLS certificate tools

## Hands-On Projects

1. **Design a Twitter-like System** - 100M users, real-time feed
2. **Design Uber Backend** - Geolocation, matching, payments
3. **Secure REST API** - Auth, validation, rate limiting
4. **GraphQL Server** - Schema design, resolvers
5. **Smart Contract** - Ethereum token, auction system
6. **Security Audit** - Find and document vulnerabilities
7. **Database Design** - Complex data model optimization
8. **Microservices Architecture** - Multiple services, communication

## Best Practices

- Document architecture decisions
- Regular architecture reviews
- Security-first thinking
- Secure coding practices
- Regular security audits
- Compliance with standards
- Incident response planning
- Continuous monitoring
- Knowledge sharing and training
