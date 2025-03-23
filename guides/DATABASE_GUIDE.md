# Database Management Guide

## Purpose
This guide outlines the database management procedures and best practices for the UNM Music Preparatory Division project.

## Database Architecture

### 1. Schema Design
```sql
-- Users Table
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    role VARCHAR(20) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Students Table
CREATE TABLE students (
    id SERIAL PRIMARY KEY,
    user_id INTEGER REFERENCES users(id),
    level VARCHAR(20) NOT NULL,
    instrument VARCHAR(50) NOT NULL,
    start_date DATE NOT NULL
);

-- Teachers Table
CREATE TABLE teachers (
    id SERIAL PRIMARY KEY,
    user_id INTEGER REFERENCES users(id),
    specialization VARCHAR(100) NOT NULL,
    availability JSON NOT NULL
);

-- Courses Table
CREATE TABLE courses (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    description TEXT,
    level VARCHAR(20) NOT NULL,
    teacher_id INTEGER REFERENCES teachers(id)
);
```

### 2. Relationships
- One-to-One
- One-to-Many
- Many-to-Many
- Inheritance

### 3. Indexes
- Primary keys
- Foreign keys
- Performance indexes
- Unique constraints

## Data Management

### 1. Data Types
- Strings (VARCHAR, TEXT)
- Numbers (INTEGER, DECIMAL)
- Dates (DATE, TIMESTAMP)
- Binary (BLOB, BYTEA)
- JSON/JSONB

### 2. Constraints
- NOT NULL
- UNIQUE
- CHECK
- FOREIGN KEY
- DEFAULT

### 3. Validation
- Data type validation
- Range validation
- Format validation
- Relationship validation

## Database Operations

### 1. Backup
```bash
# Full backup
pg_dump -U admin unm_prep > full_backup.sql

# Schema only
pg_dump -U admin -s unm_prep > schema.sql

# Data only
pg_dump -U admin -a unm_prep > data.sql
```

### 2. Restore
```bash
# Full restore
psql -U admin unm_prep < full_backup.sql

# Schema restore
psql -U admin unm_prep < schema.sql

# Data restore
psql -U admin unm_prep < data.sql
```

### 3. Maintenance
```sql
-- Vacuum
VACUUM ANALYZE;

-- Reindex
REINDEX TABLE users;

-- Update statistics
ANALYZE users;
```

## Query Optimization

### 1. Index Usage
```sql
-- Create index
CREATE INDEX idx_users_email ON users(email);

-- Create composite index
CREATE INDEX idx_students_level_instrument ON students(level, instrument);

-- Create unique index
CREATE UNIQUE INDEX idx_users_username ON users(username);
```

### 2. Query Planning
```sql
-- Explain plan
EXPLAIN ANALYZE
SELECT *
FROM users u
JOIN students s ON u.id = s.user_id
WHERE u.role = 'student';
```

### 3. Performance Tuning
- Connection pooling
- Query caching
- Index optimization
- Table partitioning

## Security

### 1. Access Control
```sql
-- Create role
CREATE ROLE readonly;

-- Grant permissions
GRANT SELECT ON ALL TABLES IN SCHEMA public TO readonly;

-- Create user
CREATE USER reporter WITH PASSWORD 'secret';

-- Assign role
GRANT readonly TO reporter;
```

### 2. Data Protection
- Encryption at rest
- Encryption in transit
- Data masking
- Audit logging

### 3. Monitoring
- Query performance
- Resource usage
- Error logging
- Security events

## Migration

### 1. Version Control
```sql
-- Version table
CREATE TABLE schema_version (
    version INTEGER PRIMARY KEY,
    applied_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    description TEXT
);

-- Track version
INSERT INTO schema_version (version, description)
VALUES (1, 'Initial schema');
```

### 2. Migration Scripts
```sql
-- Up migration
CREATE TABLE new_feature (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);

-- Down migration
DROP TABLE new_feature;
```

### 3. Deployment
- Testing migrations
- Backup before migration
- Execution plan
- Rollback plan

## Best Practices

### 1. Schema Design
- Normalization
- Naming conventions
- Documentation
- Version control

### 2. Query Design
- Index usage
- Join optimization
- Subquery optimization
- Pagination

### 3. Security
- Access control
- Data protection
- Audit logging
- Regular updates

### 4. Maintenance
- Regular backups
- Performance monitoring
- Index maintenance
- Statistics updates

## Emergency Procedures

### 1. Data Recovery
1. Stop application
2. Assess damage
3. Restore backup
4. Verify data
5. Resume service

### 2. Performance Issues
1. Identify bottleneck
2. Optimize queries
3. Update indexes
4. Monitor results
5. Document changes

### 3. Security Incidents
1. Isolate system
2. Assess breach
3. Fix vulnerability
4. Update security
5. Monitor activity

---
Last Updated: March 23, 2024
Next Review: June 23, 2024 