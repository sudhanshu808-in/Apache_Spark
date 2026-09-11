# 🚀 Apache Spark Learning Journey

<div align="center">

![Apache Spark](https://img.shields.io/badge/Apache%20Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PySpark](https://img.shields.io/badge/PySpark-FF6600?style=for-the-badge&logo=apache&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)

*Hands-on exploration of distributed data processing with Apache Spark*

</div>

---

## 📚 What I'm Building

This repository documents my practical journey through Apache Spark's distributed computing ecosystem. Rather than just theoretical notes, these are working implementations that solve real data engineering challenges.

## 🎯 Core Concepts Explored

### 🔹 Data I/O & Transformations
**Building production-grade data pipelines**

```python
# Multi-format data engineering
✓ Parquet, CSV, Delta Lake integration
✓ Schema inference and enforcement
✓ Partitioned writes for query optimization
✓ Format conversion workflows
```

**Key Skills:** Reading from multiple sources, writing optimized outputs, managing schema evolution, and partitioning strategies for performance.

---

### 🔹 Advanced Aggregations & Window Functions
**Solving complex analytical problems**

<table>
<tr>
<td width="50%">

**Ranking & Analytics**
- `row_number()`, `rank()`, `dense_rank()`
- Top-N queries per group
- Department-wise salary rankings

</td>
<td width="50%">

**Time-Series Analysis**
- `lead()` and `lag()` for trend analysis
- Moving aggregations
- Month-over-month comparisons

</td>
</tr>
</table>

**Real-world Application:** Employee salary analysis, product sales trends, and time-series forecasting patterns.

---

### 🔹 Join Strategies & Data Relationships
**Mastering distributed joins**

```
┌─────────────┐         ┌──────────────┐         ┌─────────────┐
│  Customers  │────────▶│    Sales     │────────▶│  Products   │
└─────────────┘         └──────────────┘         └─────────────┘
     Inner                  Left/Right                Outer
   Left Semi                Left Anti              Cross Join
```

Implementing:
* Customer-Sales-Product dimensional modeling
* Finding customers who haven't purchased (anti-join)
* Identifying active vs. inactive users
* Full outer joins for data reconciliation

---

### 🔹 Performance Optimization
**Understanding Spark internals**

#### The Skew Problem
```
Before:  [████████████████████] ← One executor drowning
         [█]                    ← Others idle
         [█]

After:   [████]  ← Balanced load
         [████]
         [████]
```

**Deep Dives:**
* **Repartition vs. Coalesce** - Wide vs. narrow transformations
* **Partition Management** - Controlling parallelism and file count
* **Data Skew Solutions** - Salting techniques and broadcast joins
* **Shuffle Optimization** - Minimizing network I/O

---

### 🔹 SQL & DataFrame API Duality
**Fluent in both paradigms**

Every concept implemented in:
* **PySpark DataFrame API** - For programmatic control
* **Spark SQL** - For analytical expressiveness

```python
# DataFrame API
df.groupBy("dept").agg(sum("salary"))

# Equivalent SQL
spark.sql("SELECT dept, SUM(salary) FROM employees GROUP BY dept")
```

---

## 🛠️ Technical Stack

* **Compute:** Databricks Serverless
* **Language:** Python (PySpark)
* **Storage:** Delta Lake, Parquet, CSV
* **Catalog:** Unity Catalog (UC)

## 📂 Repository Structure

```
📦 apache-spark-learnings/
├── 🎯 apache spark         # Fundamentals: I/O, transformations
├── 🪟 window_functions     # Analytics: ranking, lead/lag
├── 🔗 joins                # All join types with real scenarios
├── ⚡ repartition vs coalesce  # Performance tuning
├── 📊 group_by             # Aggregation patterns
├── 🔀 union vs union all   # Set operations
├── 🧹 unique&sorted        # Deduplication strategies
└── 🎛️ case-when            # Conditional logic
```

## 🎓 Learning Approach

**Theory → Implementation → Optimization**

1. **Understand the concept** - Why does Spark do it this way?
2. **Code it out** - Hands-on implementation with real data
3. **Optimize it** - Performance tuning and best practices
4. **Compare approaches** - DataFrame API vs. SQL, different join types, etc.

## 🚀 Next Steps

* [ ] Streaming with Structured Streaming
* [ ] Delta Lake advanced features (Time Travel, CDF)
* [ ] MLlib for distributed machine learning
* [ ] Query optimization and execution plans
* [ ] Production job orchestration

---

<div align="center">

**💡 Each notebook is a working lab - feel free to explore, fork, and experiment!**

*Building proficiency one transformation at a time* ⚡

</div>