# Copilot Instructions for Computational Finance Notebooks

## Project Overview
This workspace is focused on computational finance education, using Jupyter notebooks for hands-on exercises, simulations, and data analysis. The primary language is Python, with heavy use of numpy, pandas, and matplotlib for statistical analysis and visualization.

## Key Patterns & Structure
- **Notebooks**: Each week or topic is a separate `.ipynb` file (e.g., `Week2.ipynb`). Notebooks are sequential and build on each other.
- **Data Files**: All datasets are stored in the `dataFiles/` directory. Use relative paths (e.g., `dataFiles/sector_weights_returns.csv`) for loading data.
- **Simulation & Analysis**: Simulations use numpy for random data generation; pandas is used for tabular data manipulation; matplotlib for plotting.
- **Examples**: Code cells often demonstrate a concept, then show output. Explanatory markdown is used before code blocks.

## Developer Workflow
- **No build step**: Notebooks are run interactively. No compilation or packaging is required.
- **Testing**: There are no formal unit tests; validation is done by running cells and inspecting output.
- **Data Import**: Always use relative paths for data files. Example:
  ```python
  pd.read_csv('dataFiles/sector_weights_returns.csv')
  ```
- **Visualization**: Use `matplotlib.pyplot` for plots. Always call `plt.show()` after plotting in a cell.
- **Randomness**: For reproducibility, set numpy random seeds if deterministic results are needed.

## Conventions
- **Variable Naming**: Use descriptive, lower_snake_case for variables (e.g., `sp_ret`, `stock_ret`).
- **Cell Structure**: Each concept is introduced with markdown, followed by code. Avoid mixing unrelated topics in a single cell.
- **DataFrame Indexing**: When reading CSVs, use `index_col` to set the index if needed.
- **File Organization**: Do not move or rename data files; notebooks expect them in `dataFiles/`.

## Integration Points
- **Excel Files**: Use `pandas.read_excel` for `.xlsx` files in `dataFiles/`.
- **No external APIs**: All data is local; no web requests or external services are used.

## Examples
- Loading a CSV:
  ```python
  df = pd.read_csv('dataFiles/sector_weights_returns.csv')
  ```
- Plotting:
  ```python
  import matplotlib.pyplot as plt
  plt.plot(df['1Y_return'])
  plt.show()
  ```

## Key Files
- `Week2.ipynb`, `Week3.ipynb`, etc.: Main instructional content
- `dataFiles/`: All datasets used in notebooks

---

For AI agents: Follow the notebook structure, use relative paths, and prefer code clarity and reproducibility. If adding new data, place it in `dataFiles/` and reference it with a relative path.
