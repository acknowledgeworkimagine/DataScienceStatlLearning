### Pandas `axis=0` vs `axis=1`

In pandas:

- `axis=0` generally refers to working along the rows.
- `axis=1` generally refers to working across the columns.

For reduction functions such as `any()`:

- `df.isnull().any(axis=0)` → checks each **column** and returns one result per column.
- `df.isnull().any(axis=1)` → checks each **row** and returns one result per row.

Examples:

`df.isnull().any(axis=0)` → Which columns contain missing values?
`df.isnull().any(axis=1)` → Which rows contain missing values?

For removal functions such as `dropna()`:

- `df.dropna(axis=0)` → removes **rows** containing missing values.
- `df.dropna(axis=1)` → removes **columns** containing missing values.

Memory rule:

- With `any()`, the axis indicates the direction of reduction.
- With `dropna()`, the axis indicates what is removed.