## 0.0.1 - Initial Version (2023-10-08)

- Schedule sealed base class with subclasses for different schedule types:
  * Singular: A single occurrence
  * Daily: Repeats every _n_ days
  * Weekly: Repeats every _n_ weeks on the given weekdays (Su - Sa)
  * Monthly: Repeats every _n_ months on the given day(s) of the month
  * Yearly: Repeats every _n_ years on the specified date
- Optional `endDate` parameter to constrain the schedule