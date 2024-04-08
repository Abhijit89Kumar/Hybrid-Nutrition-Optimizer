**Hybrid Nutrition Optimizer**

**Overview**

This project provides a Python script designed to help users create nutritionally balanced meal plans within specified budget constraints. It adopts two distinct optimization approaches:

1. **Linear Programming with Gurobipy:**  
   - Leverages linear programming to calculate the optimal combination of food items that meet nutritional and budgetary needs. 
   - Offers a more deterministic solution with the ability to find other good solutions.

2. **Genetic Algorithm:**  
   - Implements a genetic algorithm to explore the solution space and find a diverse set of meal plans.
   - Provides a heuristic approach that may find solutions that linear programming might miss.

**Data Requirements**

The project requires the following data files in Excel format:

* **data.xlsx:** A spreadsheet containing:
    * **Food Column:** A list of available food items.
    * **Cost Column:** Price per serving for each food item
    * **Nutritional Columns:** Columns for different nutrients (e.g., Protein, Calories, Carbohydrates, Fat, Fiber) indicating nutrient content per serving.
    * **Integer Column:** A column with 'Y' for foods with whole-number servings  or 'N' for continuous serving sizes.
* **Sheet2 (male_data.xlsx):** Age- and gender-based nutritional requirements for males.
* **Sheet3 (female_data.xlsx):** Age- and gender-based nutritional requirements for females.

**Installation**

1. **Gurobipy:** Install the Gurobipy package using pip:
   ```bash
   pip install gurobipy
   ```
   (Ensure you have Gurobi Optimizer installed and licensed if needed)

2. **Other Dependencies:** Install other required libraries:
   ```bash
   pip install pandas numpy random
   ```

**Usage**

1. Place your Excel data files in the same directory as the Python script.

2. Run the Python script. 

3. The script will prompt you to provide the following inputs:
    * **Age**
    * **Gender (M/F)**
    * **Lower Budget Limit**
    * **Upper Budget Limit**

4. The code will run both optimization approaches:

    * **Gurobipy Optimizer:** It will output an optimal solution and potentially other good solutions within the set tolerances.

    * **Genetic Algorithm:** It will present a set of top meal plans that satisfy the constraints as best as possible.

**Example Output**

```
Optimal Solution
Food1: 1.25 servings 
Food2: 0.50 servings
...
Total Cost: $XX.XX

Other Solution #1
...
```

**Code Structure**

The Python file contains the following sections:

* **Imports:** Necessary libraries
* **Data Loading:** Reading data from Excel files
* **User Input:** Collecting user preferences
* **Gurobipy Optimizer:**
    * Model definition, variables, and constraints
    * Budget and nutritional constraints implementation
    * Optimization and solution printing
* **Genetic Algorithm**
    * Helper functions (meal plan generation, nutrient calculation, fitness evaluation)
    * Evolutionary algorithm logic (initialization, selection, crossover, mutation)
    * Presentation of results

**Customization**

You can modify the nutrient constraints and data files to align with specific dietary requirements or food lists.

**Note:**  If you are not using Gurobi, remove the relevant code sections.
