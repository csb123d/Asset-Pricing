# Asset-Pricing
## Autocallable Phoenix Product Pricing: Monte Carlo Simulation
This project implements a Python-based pricing model for a structured financial product known as the Autocallable Phoenix. The pricer uses Monte Carlo simulation to evaluate the expected value of the product under various market scenarios.

### Project Overview
An Autocallable Phoenix is a hybrid investment product combining equity-linked notes and periodic income payments, with the potential for early redemption. The payout depends on the underlying asset's performance relative to predefined barriers.

### Key Features of the Model
**Monte Carlo Simulation**: Simulates multiple price paths of the underlying asset using Geometric Brownian Motion (GBM).
**Kickout Mechanism**: Evaluates early redemption if the asset exceeds a predefined trigger level at annual observation points.
**Coupon Payments**: Calculates periodic income if conditions are met.
**Capital Protection**: Assesses the principal repayment and potential losses based on a protection barrier at maturity.
**Interactive Interface**: A user-friendly widget interface allows easy experimentation with parameters.

### How It Works
#### Pricing Workflow
##### Price Simulation:
Simulates the price path of the underlying asset using GBM.
Adjusts for drift, volatility, and random shocks.
##### Payoff Calculation: 
Tracks if the asset price meets the Kickout Barrier to trigger early redemption.
Evaluates final payouts, including principal protection, if maturity is reached.
##### Monte Carlo Aggregation:
Repeats simulations over thousands of paths to compute the average expected payoff.
##### Discounting: 
Discounts cash flows to present value using the risk-free rate.

### Code Overview
#### Main Functions
'payoff' Simulates the price evolution of the underlying asset and calculates payouts based on kickout and protection barriers.

'monteCarloPrice' Runs multiple simulations using payoff to calculate the expected price of the product.

'monte_carlo_interface' Provides an interactive widget interface to experiment with parameters and visualize results.

### How to Use
#### Setup

**Clone the repository:**

git clone <repository-url>
cd <repository-directory>

**Install dependencies:**

pip install numpy pandas ipywidgets

### Run the Simulation
Run the Jupyter Notebook or Python script and interact with the widget-based interface to:
- Define parameters like drift, volatility, barriers, and maturity.
- Compute and display the product's price.

### Parameters
t_steps: Number of time steps in the simulation.
TtM: Time to maturity (in years).
Drift: Drift of the underlying price path.
Vol: Volatility of the underlying price.
Disc: Discount rate for present value calculations.
S_0: Initial price of the underlying asset.
S_k: Kickout barrier for early redemption.
S_p: Protection barrier for principal repayment.
N: Nominal value of the investment.
I: Yearly interest rate over the nominal value.
n_simu: Number of Monte Carlo simulations.
