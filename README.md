# Bayesian Team Composition Recommendation System

This project aims to develop a **Bayesian team composition recommendation system** for Pokemon teams, where the system provides probabilistic suggestions for team members based on a subset of currently selected Pokemon. The system uses Pokemon usage statistics, such as frequency of Pokemon, item usage, and EV spreads, to make informed recommendations.

## Project Structure

- **Data Preprocessing**:  
  Organize the usage statistics into a dataset where each team is represented by the Pokemon used and their respective frequency of appearing together. This forms the input for the Bayesian model.

- **Prior Probabilities**:  
  Set prior probabilities based on the overall usage of each Pokemon. For instance, if a Pokemon is used 30% of the time, that forms the prior for it being on any given team. These priors will be updated as more information is provided (i.e., additional team members).

- **Conditioning on Known Information**:  
  Once a user provides 1 or 2 Pokemon as input, the system conditions on this information to update the likelihood of other Pokemon being chosen. This process involves using historical co-usage data between Pokemon to inform the recommendation.
  
  The model will calculate the conditional probabilities, factoring in how often different Pokemon appear together on the same team.

- **Inference**:  
  **Bayesian inference** is used to calculate posterior probabilities, updating the likelihood of a Pokemon being chosen based on the current team composition. Inference methods such as **Markov Chain Monte Carlo (MCMC)** will be used to sample from the posterior distribution and provide recommendations.

- **Evaluation and Iteration**:  
  Evaluate the system using historical team data to compare the recommendations against actual team compositions. The model will undergo iterative improvements, refining priors and the Bayesian network structure to increase the accuracy of recommendations.

## Getting Started

### Prerequisites
- Python 3.x
- Libraries:  
  - `pandas` for data handling
  - `numpy` for numerical operations
  - `scipy` for Bayesian inference
  - `networkx` for building the Bayesian network (optional)

### Usage

1. **Data Preprocessing**:  
   Prepare the dataset of Pokemon usage, including frequency of Pokemon, item usage, and EV spreads. Organize it into a format where each team composition is represented by the chosen Pokemon.
   
2. **Set Prior Probabilities**:  
   Define the prior probabilities based on the overall usage of each Pokemon.

3. **Run the Model**:  
   Input 1 or 2 Pokemon, and the system will return a list of probabilistic recommendations for additional Pokemon to complete the team.
   
4. **Inference**:  
   The Bayesian inference process updates probabilities as new team members are selected.

5. **Evaluate**:  
   Validate the system by comparing its recommendations to historical team data.

## Roadmap

1. Data preprocessing and cleaning.
2. Setting up the Bayesian model structure.
3. Implementing the inference system (MCMC, Gibbs sampling, etc.).
4. Validating and refining the model based on historical data.
5. Adding user interface (optional).

## Future Enhancements

- Incorporate items and EV spread into the recommendation model.
- Visualize the Bayesian network for better interpretability.
- Allow the system to factor in move usage alongside Pokemon for more precise team recommendations.

## Contributing

Contributions are welcome! Please feel free to submit pull requests or suggest features.

## License

This project is licensed under the MIT License.

