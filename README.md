Leclerc is a Sun Cable initiative that creates a PERT wrapper around levelised cost formulas to identify Monte Carlo trends in PERT inputs.
This package has derived work done by Heiko Onnen which can be found at: https://towardsdatascience.com/python-powered-monte-carlo-simulations-fc3c71b5b83f and https://towardsdatascience.com/python-scenario-analysis-modeling-expert-estimates-with-the-beta-pert-distribution-22a5e90cfa79.

To use this package, call a formula and add the parameters. For inputs that have uncertainty, apply the PERT parameter. The output should give a bokeh html showcasing a histogram of the levelised cost parameter and PDF plots for inputs. 

Example Case:

Running a test case on an LCOS requiring example inputs: 

1. Create a function for LCOS that calculates the formula:
lcos("Type", "Name", useful_life, nominal_discount_rate, inflation_rate, capacity_MWh, capital_cost, cycles_per_year max_depth_of_discharge_fraction, degradation_fraction, energy_input_price, round_trip_efficiency, fixed_o_m_costs_yearly)

2. Add a PERT Distribution on any input such as PERT(min=?,mode=?,max=?,label=?)

3. Run: LCOS = probabilistic_lcos("LCOS", "Name", 40, 8, PERT(min=1, mode=2, max=3, label="Inflation"), 20, 400000, 273, 1, 0.0148, 20, 0.931, 139416958.7)
