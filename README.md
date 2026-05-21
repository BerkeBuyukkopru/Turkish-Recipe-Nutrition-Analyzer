# Turkish Recipe Nutritional Analyzer

An intelligent, NLP-powered tool designed to analyze Turkish recipes, extract ingredients and their quantities, and calculate detailed nutritional values (Calories, Fat, Carbohydrates, Protein, Sugar, and Fiber). 

This project uses the Stanford **Stanza** NLP library to perform lemmatization and part-of-speech (POS) tagging on Turkish texts. It matches the extracted ingredients against a local database, applying smart fuzzy matching (via `difflib`) to autocorrect spelling mistakes.

## Features
- **Natural Language Parsing:** Automatically detects standard units (grams, kg, ml) as well as Turkish household units (yemek kaşığı, su bardağı, dilim, adet).
- **Smart Typo Correction (Fuzzy Matching):** If an ingredient is misspelled (e.g., "domatez"), the system calculates its similarity with the database. If it's highly similar (≥ 80%), it autocorrects and includes it in the calculations. Otherwise, it suggests alternatives.
- **Portion Control:** Allows users to input the number of servings and calculates both total and per-serving nutritional values.
- **Data Visualization:** Generates a pie chart to visualize the macronutrient distribution (Fat, Carbohydrates, Protein) of the recipe.
- **Interactive Notebook:** Ready to use locally or on Google Colab with an interactive UI built via `ipywidgets`.

## Installation

1. Clone the repository:
```bash
git clone https://github.com/BerkeBuyukkopru/Calories_and_Nutritional_Analysis_of_Recipes.git
cd Calories_and_Nutritional_Analysis_of_Recipes
```

2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

*Note: The first time you run the project, the Stanza Turkish models will be downloaded automatically (approx. 500MB).*

## Usage

**Option 1: Jupyter Notebook (Recommended)**
Open the `Calories_and_Nutritional_Analysis_of_Recipes.ipynb` file in Jupyter Notebook, VS Code, or Google Colab. Run all the cells. An interactive text box and button will appear at the bottom where you can type your recipe in Turkish.

**Option 2: Python Script**
You can import the module or use the logic within `run_analysis.py` to parse texts programmatically:

```python
import pandas as pd
from run_analysis import malzeme_ve_miktar_bul, besin_degerleri_hesapla

# Load the database
df = pd.read_csv('Yemek_Veri_Tabanı.csv')

# Parse recipe
recipe_text = "2 yemek kaşığı zeytinyağı ve 1 adet domates"
ingredients = malzeme_ve_miktar_bul(recipe_text)

# Calculate nutrition
totals, not_found = besin_degerleri_hesapla(ingredients, df)
print(totals)
```

## Database structure
The calculations are based on the provided `Yemek_Veri_Tabanı.csv` database, which contains basic ingredients. You can expand the database by adding new ingredients with their values per 100g.
