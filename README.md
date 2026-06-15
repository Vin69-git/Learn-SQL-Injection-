# Relational Database SQL Injection (SQLi) Authentication Bypass Analysis

## Project Overview
This repository documents the structural analysis, identification, and execution mechanics of an application-layer SQL Injection (SQLi) Authentication Bypass attack. The primary objective of this laboratory is to demonstrate how unvalidated user string inputs can break out of application-defined query containers, mutate backend database logic tables, and successfully hijack administrative sessions within a target sandbox web infrastructure.

## Technical Artifacts Index
* SQL_Injection_Tutorial.pdf: End-to-end visual reporting, capturing raw interface requests, mutated server-side logical queries, and administrative portal breakout screens.
* Setup.md: Target application baseline deployment configurations and platform testing profiles.
* Vulnerable_App.md: Verified threat intelligence tracking metrics and target endpoints hosting identified input sanitization defects.

---

## Featured Penetration Testing Case Study: Login Panel Logic Overrides

### 1. Backend Query Mapping & Identification
An assessment of the target application's authentication module (`login.jsp`) identified that input parameters entered into the front-end forms were mapped directly into a dynamic relational query string framework on the database engine server:
```sql
SELECT * FROM users WHERE username = 'USER_INPUT' AND password = 'PASSWORD_INPUT'
