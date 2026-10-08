# 1. Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data
**Goal:**
Retrieve hidden/unreleased products

**Injection point:**
category parameter

**Original query:**
SELECT * FROM products WHERE category = 'Gifts' AND released = 1

**Payload:**
' OR 1=1--

**Result:**
The application displayed unreleased products

# 2. Lab: SQL injection vulnerability allowing login bypass
**Goal:**
Log in to the application as the administrator user. 

**Injection point:**
username parameter

**Payload:**
administrator'--

**Result:**
The application logged in as administrator.

