### MUCH faster rbind

instead of doing:

```R
df_combine = data.frame()
for (file in files){
    df_curr = read.csv(file)
    df_combine = rbind(df_combine, df_curr)
```

do 

```R
library(data.table)
df_list = list()
for (file in files){
    df_list[file] = read.csv(file)
df_combine = rbindlist(df_list)
```

it's much faster!!
