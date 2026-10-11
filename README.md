# 🦷 Mercy Dental Stock — Inventory Management System

### Flask | Python | SQLite | HTML | Jinja

## 📌 Project Overview

Mercy Dental Stock is a Flask-based dental inventory management application designed to help clinics monitor stock levels, track expiration dates, and manage inventory efficiently.

This repository is a fork of the original project by [bunthahun](https://github.com/bunthahun/mercy-dental-stock).

I forked this repository to gain hands-on experience navigating an existing codebase, understanding full-stack application architecture, and contributing improvements using Git and GitHub.

## 🛠️ Tech Stack

- **Backend:** Python, Flask
- **Database:** SQLite
- **Frontend:** HTML, Jinja templates, CSS
- **Version Control:** Git & GitHub

## 🚀 My Contributions

### Feature: Expiring Today Inventory Status

**Pull Request:** [#1 — Expiration Status Improvements](https://github.com/jessicalim657/mercy-dental-stock/pull/1)

**Problem**

The original inventory classification logic grouped items expiring today (`days_left == 0`) with those expiring within the next 60 days.

This made it difficult to distinguish items requiring immediate attention from those approaching expiry.

**Solution**

Introduced a separate `expiring_today` classification to improve the granularity of expiry tracking.

Changes included:

- Updated `evaluate_status()` to handle items expiring today.
- Added `expiring_today_count` to inventory statistics.
- Updated status labels and export filename mappings.
- Added an Expiring Today option to the frontend inventory filter.
- Refined the Expiring Soon classification to cover 1–60 days.

Updated Classification Logic

```python
if days_left < 0:
    status = 'expired'
elif days_left == 0:
    status = 'expiring_today'
elif days_left <= 60:
    status = 'expiring_soon'
else:
    status = 'good_expiry'
```

This allows the application to distinguish between expired items, items expiring today, and items approaching expiry.

## 🧠 Key Learnings

This project provided practical experience in:

- Navigating and understanding an unfamiliar Python codebase.
- Tracing feature dependencies across backend logic and frontend templates.
- Working with Flask, SQLite and Jinja.
- Applying conditional logic and boundary-case reasoning.
- Using Git for branching, staging, committing, cherry-picking and pushing changes.
- Creating, reviewing and merging a GitHub pull request.

A key takeaway was learning that implementing even a small feature can require modifications across multiple interconnected parts of an application.

## 🔍 Future Improvements

- Write automated unit tests for expiry classification.
- Test inventory filters and dashboard statistics end-to-end.
- Explore improvements to stock-alert functionality.
- Refactor duplicated status-classification logic for maintainability.
- Review security and configuration before any deployment.

## 🙏 Acknowledgements

Original project developed by [bunthahun](https://github.com/bunthahun/mercy-dental-stock).

This fork is maintained for educational purposes and independent software engineering practice. Credit for the original application and its architecture belongs to the original developer.
