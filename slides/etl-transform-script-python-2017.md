##  ETL Transform Script (Python 2017)

Python transformation script using the Pandas package.

<br>

<!-- Attempt 1.
```
import pandas as pd

df = pd.read_excel("sales_transactions.xlsx")

df.groupby('order')["ext price"].sum()

# order
# 10001     576.12
# 10005    8185.49
# 10006    3724.49
# Name: ext price, dtype: float64

order_total = df.groupby('order')["ext price"].sum().rename("Order_Total").reset_index()

df_1 = df.merge(order_total)

df_1["Percent_of_Order"] = df_1["ext price"] / df_1["Order_Total"]
```
Attempt 2.
-->

```
import pandas as pd
df = pd.read_excel("sales_transactions.xlsx")
df.groupby('order')["ext price"].transform('sum')
df["Order_Total"] = df.groupby('order')["ext price"].transform('sum')
df["Percent_of_Order"] = df["ext price"] / df["Order_Total"]
# Or Combine them.
# df["Percent_of_Order"] = df["ext price"] / df.groupby('order')["ext price"].transform('sum')
```

<!-- log:
```
0      576.12
1      576.12
2      576.12
3     8185.49
4     8185.49
5     8185.49
6     8185.49
7     8185.49
8     3724.49
9     3724.49
10    3724.49
11    3724.49
dtype: float64
``` -->

<br>

![](resources/images/data/transform-example.png) <!-- .element width="50%" -->

<p>
<span>
Data Transformation Diagram.
</span><!-- .element: class="caption" -->
</p><!-- .element: class="caption-wrapper" -->
