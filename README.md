- 👋 Hi, I’m @jpowe23
- 👀 I’m interested in ...# Import necessary libraries
import pandas as pd
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split

# Load the data into a dataframe
df = pd.read_csv("nba_data.csv")

# Split the data into features (X) and labels (y)
X = df.drop("winner", axis=1)
y = df["winner"]

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Train a logistic regression model on the training data
model = LogisticRegression()
model.fit(X_train, y_train)

# Evaluate the model's performance on the testing data
score = model.score(X_test, y_test)
print("Accuracy:", score)

# Make predictions and calculate the best odds for a future game
team_1_stats = [...]  # input statistical and Vegas odds data for team 1
team_2_stats = [...]  # input statistical and Vegas odds data for team 2
probabilities = model.predict_proba([team_1_stats, team_2_stats])
print("Probability of Team 1 winning:", probabilities[0][1])
print("Probability of Team 2 winning:", probabilities[1][1])
odds_team_1 = -250 / probabilities[0][1]
odds_team_2 = 200 / probabilities[1][1]
print("Odds for Team 1:", odds_team_1)
print("Odds for Team 2:", odds_team_2)

- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
jpowe23/jpowe23 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
