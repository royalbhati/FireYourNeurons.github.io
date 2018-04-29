# What is One Hot Encoding and when is it benificial?

If you are an Machine Learning or Deep Learning Enthusiast you have been reading or hearing this term _One Hot Encoding_ a lot.

So what exactly this thing is ?

**Origin**-One-hot originally comes from electronics - one-hot meaning there's only 1 'hot' or 'on' value in this list, while the rest are 'cold'

### In Data Science One hot encoding basically transforms categorical features to a format that works better with machine learning algorithms.

```
╔═════════════╦════════════════╦
║ Gender      ║Population      ║
╠═════════════╬════════════════╣
║ MALE        ╬       100      ║
║ FEMALE      ╬       500      ║
║ Unspecified ╬       50       ║     
╚═════════════╩════════════════╩
```
Let us say we have a Dataframe with two columnns Gender and Population we convert the Gender column into its Categorical Values so Dataframe now becomes

```

╔═════════════╦════════════════╦══════════╗ 
║ Gender      ║Categoricalvalue║Population║
╠═════════════╬════════════════╣══════════║ 
║ MALE        ╬      1         ║ 100      ║
║ FEMALE      ╬      2         ║ 500      ║
║ Unspecified ╬      3         ║ 50       ║
╚═════════════╩════════════════╩══════════╝
```
Now Male is assigned to 1 ,Female to 2 and so on but does that make any sense?

Algorithm will interpret that Female is higher than Male

Is it a valid interpretation?

Sorry Feminists but **NO** its not
That does not really make any sense in terms of value and feature because all of them are completely independent features.

Algorithm will continue building its prediction on these interpretation and it won't end good
so we need to Encode every caegorical value into separate binary variables.

```

╔════╦══════╦══════╦════════╦
║MALE║FEMALE║ Usp  ║  Pop.  ║
╠════╬══════╬══════╬════════╬
║ 1  ╬ 0    ╬ 0    ║ 100    ║
║ 0  ╬ 1    ╬ 1    ║ 500    ║
║ 0  ╬ 0    ╬ 1    ║ 50     ║
╚════╩══════╩══════╩════════╝

```
Now every Gender has its own say separately

### When is it benificial?
This works good with almost every machine learning algorithms. but there are few algorithms that can handle categorical values natively like Decision Trees and Random Forests so they don't require One-hot encoding but some Clustering and Regression algorithms needs this for better results.




