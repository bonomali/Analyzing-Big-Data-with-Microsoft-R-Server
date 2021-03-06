# Exercises

We learned how to use the `rxSummary` function to summarize the data. If we pass the formula `~ .` to `rxSummary`, we get a summary of all the column in the data. This summary consists of counts for `factor` columns and numeric summaries for `numeric` and `integer` columns (`character` columns don't have any summary statistics).

Using the CSV for the sample corresponding to the month of January 2016 of the NYC taxi data, perform the following analysis:
  
(1) Convert the CSV file for that month to XDF (using `rxImport`) then run `rxSummary` to get a summary of all its columns. Store the summary in an object called `sum_xdf` for later use. Use `system.time` to see how long it takes to do both the conversion and summary **together**.

```R
input_csv <- 'yellow_tripsample_2016-01.csv'
input_xdf <- 'yellow_tripsample_2016-01.xdf'

## your code goes here

file.remove(input_xdf) # remove the file to keep folder clean
```

(2) Run `rxSummary` directly on the CSV file for that month, storing the result in an object called `sum_csv` for later use. Use `system.time` to time how long it takes to summarize the CSV file.

(3) Compare the runtime in part (1) to part (2). And specify which has a shorter runtime.

```R
rt_xdf - rt_csv
```

(4) Extract the summaries for the columns `tip_amount`, `fare_amount`, and `total_amount` from `sum_xdf` and store it in a `data.frame` called `amt_xdf`. Extract the same information from `sum_csv` and store it in a `data.frame` called `amt_csv`. Compare the two `amt_xdf` and `amt_csv` by taking their difference (only keeping `numeric` columns).
