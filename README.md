# clintell
# MNIST Model Evaluation Project

This project involves the development of four different predictive models for the MNIST dataset and providing an interactive program for users to evaluate these models.

## Project Structure

- `notebook.ipynb`: Jupyter Notebook containing the data exploration, preprocessing, model training, and validation.
- `README.md`: Explanation of the project structure and decision-making process.

## Models Developed

1. Logistic Regression
2. Random Forest
3. Neural Network
4. Bayesian Logistic Regression

## Decision Making

### Data Preprocessing
- The MNIST dataset was normalized and split into training, validation, and test sets.
- Standardization was applied to ensure better model performance.

### Model Selection
- **Logistic Regression**: Chosen for its simplicity and interpretability.
- **Random Forest**: Selected for its ability to handle non-linear relationships.
- **Neural Network**: Implemented to capture complex patterns in the data.
- **Bayesian Logistic Regression**: Utilized to incorporate prior information and provide probabilistic predictions.

### Code Structure
- The code is organized into functions and scripts to maintain modularity and readability.
- Standard coding practices such as PEP 8 were followed.

## Running the Project

1. Open and run `notebook.ipynb` to see the data exploration, preprocessing, and model training steps.
2. Follow the interactive prompts to choose and evaluate models on random samples from the MNIST dataset.

## Conclusion

The project demonstrates the application of data science techniques and best coding practices to develop and evaluate predictive models.



## Justification of the Analysis

If we talk about model selection it means that there is uncertainty about the true model and each elaborated model can be just a potential model. In order to be coherent with probability theory which is the one we will guide to the final selection we have to consider a Bayesian approach. We assume here that a priori all models have the same probability and based on the fit of each model in predicting each digit we calculate the model posterior probability. We have a total of $2^p$ models because we consider all combinations of the $p$ DL models. As a summary of the probability distribution on models we consider the overall probability of each DL model in all the $2^p$ models. This probability, called he inclusion probability, is the sum of the probability of each model in which the single DL model appear. With the inclusion probability we can do two things:

1. We can select and justify the selection with the most probable model by considering the DL model with the largest inclusion probability and this concludes the selection of the model.
2. If the goal is to predict, selecting a model makes almost no sense and better consider many models to predict the response. With model posterior probability we can predict the response by calculating the prediction from each of the $2^p$ models and averaging these predictions according to their posterior model probabilities. This lead to a better prediction.

The Bayesian analysis automatically accomopades for:
1. model goodness of fit: the more the model fit the data the more is probable among the model with the same complexity;
2. model complexity: the more complex is the model and the less is probable among the model with the same goodness of fit.

In the end using Bayesian approach we can have the most probabile prediction and we also know how much is probable. We also know that from Hartigan 1966 the Bayesian approach is superior in terms of frequentist performance. In fact we need a less sample size to achieve a model that perform better in the test set than other models which are not based on the Bayesian logic and have the same degree of complexity.

