# Oscar Nomination Predictor

A machine learning project that predicts nomination and win probabilities for selected Academy Award feature-film categories using movie characteristics such as budget, genre, runtime, original language, release year, and release month.

## Predictions

The predictor estimates:

- Any selected feature-film nomination
- Any selected feature-film win
- Best Picture nomination/win
- Animated Feature nomination/win
- International Feature nomination/win
- Documentary Feature nomination/win

## Model

The project uses Logistic Regression with Scikit-learn.

Nomination probabilities are calibrated using `CalibratedClassifierCV`.

Win probabilities are calculated using:

```text
P(win) = P(nomination) × P(win | nominated)
```

Production budgets are adjusted to 2025 USD using CPI.

## Datasets

The raw datasets are not included in this repository.

Download them separately and place them in the same folder as the notebook:

- **TMDb movies:** [Kaggle – Full TMDB Movies Dataset](https://www.kaggle.com/datasets/asaniczka/tmdb-movies-dataset-2023-930k-movies)
  - Expected filename: `TMDB_all_movies.csv`

- **IMDb:** [IMDb Datasets](https://datasets.imdbws.com/)
  - Download `title.basics.tsv.gz`
  - Extract it as `title.basics.tsv`

- **Academy Awards:** Kaggle Oscar dataset used for the project
  - Expected filename: `full_data.csv`

## Running

Install the required packages:

```bash
pip install pandas scikit-learn jupyter
```

Open:

```text
oscar_prediction.ipynb
```

Run the cells from top to bottom.

At the end, run:

```python
predict_movie()
```

Then enter the movie's information when prompted.

## Example Output

```text
Example Movie

Any feature-film nomination     19.1%
Any feature-film win             4.0%

Best Picture nomination         17.8%
Best Picture win                 0.6%

Animated Feature nomination      1.0%
Animated Feature win             0.9%
```

## Limitations

This is an experimental machine learning project, not an official Oscar forecasting system.

Predictions are based on historical patterns and do not include factors such as critics' reviews, awards campaigns, cast/director reputation, or marketing budgets.