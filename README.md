# Cloud Computing Lab 5 – Assignment 1

## AWS RDS PostgreSQL Integration with Redmine on EC2

**Student:** Santo Xavier  
**Roll No.:** 10699  
**Class:** T.E. Computer Engineering – COMPS B  
**Subject:** Cloud Computing  
**Academic Year:** 2026–2027

---

## 1. Objective

The objective of this assignment is to deploy an AWS RDS PostgreSQL database and connect it to the Redmine application deployed on the Lab 4 Amazon EC2 instance.

The assignment demonstrates:

- AWS RDS PostgreSQL deployment
- Secure EC2-to-RDS connectivity
- Migration of the existing Lab 4 Redmine PostgreSQL database to RDS
- Redmine application connectivity with RDS
- Create, Read, Update and Delete (CRUD) operations
- Security Group based database access control

---

## 2. Architecture

The application architecture used for this assignment is:

```text
                    Internet / Client
                           |
                           | HTTP : 80
                           v
                 +----------------------+
                 |   Amazon EC2         |
                 |   redmine-lab4       |
                 |                      |
                 |   Nginx : 80         |
                 |       |              |
                 |       v              |
                 |   Redmine / Puma     |
                 |   127.0.0.1:3000    |
                 +----------+-----------+
                            |
                            | PostgreSQL : 5432
                            | SSL
                            v
                 +----------------------+
                 |   Amazon RDS         |
                 |   PostgreSQL         |
                 |   redmine-lab5-db    |
                 |   Database: lab5db   |
                 +----------------------+
