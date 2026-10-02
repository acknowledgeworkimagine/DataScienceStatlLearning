## Pandas: Single vs Double Brackets

In pandas, the brackets used to select columns determine the type and dimensionality of the result. Using `df["column"]` returns a **Series**, which is 1D with shape `(n_samples,)`. Using `df[["column"]]` returns a **DataFrame**, which is 2D with shape `(n_samples, 1)`. Selecting several columns, such as `df[["column1", "column2"]]`, also returns a 2D DataFrame, with shape `(n_samples, 2)`.

General rule:

`["column"]` → Series → 1D  
`[["column"]]` → DataFrame → 2D  
`[["column1", "column2"]]` → DataFrame → 2D

Example:

If

`df = pd.DataFrame({"height": [170, 180, 175], "weight": [70, 85, 75]})`

then:

`df["height"]` → Series with shape `(3,)`

`df[["height"]]` → DataFrame with shape `(3, 1)`

`df[["height", "weight"]]` → DataFrame with shape `(3, 2)`

This distinction matters in machine learning because many scikit-learn methods expect predictor data `X` in 2D form: `(n_samples, n_features)`. This single-bracket vs double-bracket behavior is specific to pandas, although the general concepts of 1D and 2D data also apply to NumPy and other machine-learning libraries.