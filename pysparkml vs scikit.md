
# Scikit-learn vs PySpark ML

## 1. Overall Comparison

| Comparison | Scikit-learn | PySpark ML |
|---|---|---|
| Full name | Scikit-learn | Apache Spark Machine Learning |
| Language | Python | Python API (PySpark) |
| Programming language underneath | Python, C, Cython | Python API, Spark engine primarily Scala/JVM |
| Processing | Mainly single-machine | Distributed computing |
| Data structures | NumPy arrays, Pandas DataFrames, Series | Spark DataFrames, RDDs |
| Dataset handling | Pandas / NumPy | Spark SQL DataFrames |

---

## 2. Function-wise Comparison

| Operation | Scikit-learn | PySpark ML |
|---|---|---|
| Load dataset | `pd.read_csv()` | `spark.read.csv()` |
| View records | `df.head()` | `df.show()` |
| Dataset information | `df.info()` | `df.printSchema()` |
| Dataset dimensions | `df.shape` | `df.count()` + `len(df.columns)` |
| Check null values | `df.isnull().sum()` | `df.filter(col("Age").isNull()).count()` |
| Remove null values | `df.dropna()` | `df.dropna()` |
| Fill null values | `df.fillna()` | `df.fillna()` |
| Remove duplicates | `df.drop_duplicates()` | `df.dropDuplicates()` |
| Select features | `df[['Age','Salary']]` | `df.select()` |
| Rename columns | `df.rename()` | `df.withColumnRenamed()` |
| Create column | `df['new'] = ...` | `df.withColumn()` |
| Label encoding | `LabelEncoder()` | `StringIndexer()` |
| One-hot encoding | `OneHotEncoder()` | `OneHotEncoder()` |
| Feature scaling | `StandardScaler()` | `StandardScaler()` |
| Combine features | `X = df[features]` | `VectorAssembler()` |
| Train-test split | `train_test_split()` | `randomSplit()` |
| Create model | Algorithm class | Algorithm class |
| Train model | `model.fit(X,y)` | `model.fit(df)` |
| Prediction | `model.predict(X)` | `model.transform(df)` |
| Evaluation | `r2_score()`, `accuracy_score()`, `mean_squared_error()` | `RegressionEvaluator()`, `MulticlassClassificationEvaluator()` |
