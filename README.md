Salary Prediction for Tech World - A Udacity Project
This is a repository that includes the details of the project that predicts Salary in "Stack Overflow Annual Developer Survey" data

Motivation:
The project is created to predict annual salary based on various factors. What really affects a developer’s salary? The dataset includes a wide range of factors that allowed me to see how different factors influence earnings.

Questions of Interest
1.Does the age group have an impact on salary?
2.Does the number of known programming languages affect salary?
3.Does being a People Manager have an impact on salary?

Data
Official site (choose 2023 → Download Full Data Set (CSV)): https://survey.stackoverflow.co/
Update the file path in the script if needed.

Acknowledgments:
The dataset used in this project is sourced from the Stack Overflow Developer Survey, which provides valuable insights into developers' experiences, skills, and salaries.

For further reading:
Check out the blog post: Predicting Developer Salaries: What Matters Most

How to run
Download the CSV.
Open Proje_Final.ipynb.
Edit the line CSV_PATH = '/survey_results_public.csv.csv' and run the code
Technology Requirements
pandas, numpy, scikit-learn, matplotlib, seaborn
Notes
All columns are included (one-hot encoding for categoricals).
RandomForestRegressor for easy feature importances.
