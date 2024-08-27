# CRR

The Cox-Ross-Rubinstein (CRR) model is a binomial tree model used to price options, including those on fixed income securities such as bonds. The CRR model is an extension of the simple binomial option pricing model, providing a method to model the evolution of an asset's price or an interest rate over time in a discrete manner. It is particularly useful for pricing options with complex features like callability or putability in bonds.


The CRR model uses a binomial tree to represent the possible paths an asset's price or an interest rate can take over time. At each step, the price can move up by a factor u or down by a factor d.

Up and Down Factors:
The price of the underlying asset can move up by a factor u or down by a factor d at each step in the binomial tree.
The up factor u and the down factor d are given by:
u = exp(σ * sqrt(Δt))
d = 1 / u
Where:
σ (sigma) is the volatility of the asset.
Δt is the length of the time step.

Risk-Neutral Probability:
The risk-neutral probability p of an upward movement in the asset price is given by:
p = (exp(r * Δt) - d) / (u - d)
Where:
r is the risk-free interest rate.
u and d are the up and down factors.
Steps to Price an Option Using the CRR Model

Construct the Binomial Tree:
Model the possible price paths of the asset using the up and down factors. The asset price at each node is calculated as:
S_t = S_0 * u^(number of up moves) * d^(number of down moves)

Calculate Option Payoff at Maturity:
At the final nodes (maturity), calculate the option payoff. For a call option, the payoff is:
Payoff = max(S_T - K, 0)
Where K is the strike price.

Backwards Induction:
Starting from the final nodes, move backward through the tree. The option value at each node is calculated as the present value of the expected option value at the next step:
V_t = exp(-r * Δt) * (p * V_up + (1 - p) * V_down)
Where V_up and V_down are the option values at the next step if the price moves up or down, respectively.

Option Price:
The option price is obtained at the root of the tree, which represents the present value of the option.
