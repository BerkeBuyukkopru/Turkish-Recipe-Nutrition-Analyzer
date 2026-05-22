# Turkish Recipe Nutritional Analyzer

A lightweight NLP-based Python project that analyzes Turkish recipe texts, extracts ingredients and their quantities, and calculates approximate nutritional values such as calories, fat, carbohydrates, protein, sugar, and fiber.

The project uses **Stanford Stanza** for Turkish natural language processing and matches detected ingredients with a local nutrition database.

### Recipe Input

<img width="1735" height="235" alt="Recipe input form" src="https://github.com/user-attachments/assets/76b17942-caee-4cbb-9463-8fd11c61701f" />

### Analysis Output

<img width="1226" height="630" alt="Nutrition analysis output" src="https://github.com/user-attachments/assets/6a8e755b-9071-4900-9f50-a5b93c2ca17d" />

## About the Project

Turkish Recipe Nutritional Analyzer is a small NLP-based recipe analysis project developed with Python. It processes Turkish recipe texts, detects ingredients and quantities, converts supported measurement units into approximate gram values, and calculates nutritional values using a local food database.

The main goal of this project is to demonstrate how natural language processing can be used to extract structured ingredient data from unstructured Turkish recipe text.

## Features

- Extracts ingredients and quantities from Turkish recipe texts
- Supports common units such as grams, kilograms, milliliters, tablespoons, glasses, slices, and pieces
- Uses Turkish NLP with Stanford Stanza for lemmatization and part-of-speech tagging
- Matches detected ingredients with a local nutrition database
- Handles simple spelling mistakes with fuzzy matching
- Calculates total and per-serving nutritional values
- Visualizes macronutrient distribution with a pie chart
- Designed for use in Jupyter Notebook or Google Colab, with the main analysis logic also available as a Python file

## Technologies Used

- Python
- Pandas
- Matplotlib
- Stanford Stanza
- ipywidgets
- Jupyter Notebook / Google Colab

## How It Works

1. The user enters a Turkish recipe text.
2. The text is processed with Stanford Stanza.
3. Quantities, measurement units, and ingredient names are extracted.
4. Supported measurement units are converted into approximate gram values.
5. Extracted ingredients are matched with the local nutrition database.
6. Total and per-serving nutritional values are calculated.
7. Macronutrient distribution is visualized with a pie chart.

## Installation

Clone the repository:

```bash
git clone https://github.com/BerkeBuyukkopru/Calories_and_Nutritional_Analysis_of_Recipes.git
cd Calories_and_Nutritional_Analysis_of_Recipes
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

> The first time you run the project, Stanford Stanza will download the Turkish language model automatically. This requires an internet connection and may take some time.

## Usage

### Jupyter Notebook / Google Colab

Open the notebook file:

```text
Calories_and_Nutritional_Analysis_of_Recipes.ipynb
```

Run all cells, enter a Turkish recipe text, select the number of servings, and click the **Hesapla** button.

### Python File

You can also review the main analysis logic from:

```text
run_analysis.py
```

This file contains the same core logic used in the notebook. The project is primarily intended to be run through the notebook interface, but the Python file can be useful for understanding or reusing the implementation. Make sure the `Yemek_Veri_Tabanı.csv` file is located in the same project directory.

## Example

Example input:

```text
2 yemek kaşığı zeytinyağı, 1 adet domates ve 100 gram tavuk göğsü
```

The project detects the ingredients, converts the amounts into grams, matches them with the local nutrition database, and calculates the total nutritional values.

Example detected ingredients:

| Ingredient | Amount |
|---|---:|
| zeytinyağı | 30 g |
| domates | 100 g |
| tavuk göğsü | 100 g |

## Dataset

The project uses a local CSV file named `Yemek_Veri_Tabanı.csv`.

The dataset contains ingredient names and nutritional values per 100 grams, including:

- Calories
- Fat
- Carbohydrates
- Protein
- Sugar
- Fiber

You can expand the dataset by adding new ingredients with their nutritional values.

## Limitations

- Nutritional values are approximate and depend on the local dataset.
- Household units such as pieces, slices, and glasses are converted using fixed average gram values.
- Very complex recipe sentences may not always be parsed correctly.
- Ingredients that do not exist in the dataset may be skipped or suggested as alternatives.
- This project is not intended for medical or professional dietary use.

## Author

Developed by **Berke Büyükköprü**.

- GitHub: [BerkeBuyukkopru](https://github.com/BerkeBuyukkopru)
- LinkedIn: [Berke Büyükköprü](https://www.linkedin.com/in/berke-buyukkopru/)
