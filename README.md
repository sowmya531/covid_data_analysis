# COVID-19 Data Analysis Practice using Pandas

## Overview

This project contains basic data analysis operations performed on a COVID-19 dataset using Python Pandas. The practice covers filtering, grouping, sorting, aggregation functions, and data manipulation techniques.

---

# Libraries Used

```python
import pandas as pd
```

---

# Dataset Used

COVID-19 dataset containing:

* Region
* Confirmed Cases
* Deaths
* Recovered Cases
* Date

---

# Questions Practiced

## Q1) Show the number of Confirmed, Deaths and Recovered cases in each Region

### Code

```python
covid.groupby('Region')[['Confirmed', 'Deaths', 'Recovered']].sum()
```

### Explanation

* `groupby('Region')` → Groups data region-wise.
* `[['Confirmed','Deaths','Recovered']]` → Selects required columns.
* `.sum()` → Calculates total cases for each region.

---

## Q2) Remove all the records where the Confirmed Cases is Less Than 10

### Code

```python
covid = covid[~(covid.Confirmed < 10)]
```

### Explanation

* `covid.Confirmed < 10` → Finds records with confirmed cases less than 10.
* `~` → Negation operator used to remove those records.
* Result keeps only records with confirmed cases greater than or equal to 10.

---

## Q3) In which Region, maximum number of Confirmed cases were recorded?

### Code

```python
covid.groupby('Region')['Confirmed'].max().sort_values(ascending=False)
```

### Explanation

* `groupby('Region')` → Groups data by region.
* `max()` → Finds maximum confirmed cases.
* `sort_values(ascending=False)` → Displays highest values first.

---

## Q4) In which Region, minimum number of Deaths cases were recorded?

### Code

```python
covid.groupby('Region')['Deaths'].min().sort_values()
```

### Explanation

* `min()` → Finds minimum death cases in each region.
* `sort_values()` → Sorts values in ascending order.

---

## Q5) How many Confirmed, Deaths & Recovered cases were reported from India till 29 April 2020?

### Code

```python
covid[covid.Region == 'India'][['Confirmed', 'Deaths', 'Recovered']]
```

### Explanation

* Filters records for India.
* Displays Confirmed, Deaths, and Recovered columns.

---

## Q6-A) Sort the entire data with respect to Confirmed cases in ascending order

### Code

```python
covid.sort_values(by='Confirmed')
```

### Explanation

* `sort_values(by='Confirmed')` → Sorts data based on confirmed cases.
* Default sorting order is ascending.

---

## Q6-B) Sort the entire data with respect to Recovered cases in descending order

### Code

```python
covid.sort_values(by='Recovered', ascending=False)
```

### Explanation

* `ascending=False` → Sorts values in descending order.
* Displays highest recovered cases first.

---

# Concepts Learned

* Data Filtering
* Grouping using `groupby()`
* Aggregation Functions (`sum`, `max`, `min`)
* Sorting using `sort_values()`
* Selecting Multiple Columns
* Conditional Filtering

---

# Aggregation Functions Used

| Function | Purpose                         |
| -------- | ------------------------------- |
| `sum()`  | Calculates total values         |
| `max()`  | Finds maximum value             |
| `min()`  | Finds minimum value             |
| `agg()`  | Performs aggregation operations |

---

# Conclusion

This practice helped in understanding important Pandas operations used for real-world data analysis tasks such as filtering, sorting, grouping, and aggregation on COVID-19 datasets.
