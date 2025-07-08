# Fast followers? Speed contagion: Assessing the Impact of the Montreal F1 Grand Prix on High-Speed Collision Rates (2000–2022)

This project evaluates the potential influence of the Montreal Formula 1 Grand Prix on high-speed collision rates in Quebec from 2000 to 2022. We explore whether temporal spikes in dangerous driving behavior are associated with the F1 event, using a variety of causal inference and time-series modeling approaches.

## Project Structure

### [`step1_weather_vars.html`](./step1_weather_vars.html)

**Weather Variables and Event Setup**

* Identifies Grand Prix dates by year and determines availability based on whether the event occurred.
* Defines pre/post-event time windows and day-of-week controls.
* Links these periods to weather data from nearby meteorological stations.
* Merges with high-speed collision data from provincial sources.

### [`step1_5_weather_vars.html`](./step1_5_weather_vars.html)

**Time-Series Construction and Exploration**

* Collapses weather and collision variables into structured time-series datasets.
* Evaluates temporal dynamics including autocorrelation and seasonality.
* Prepares inputs for advanced modeling in later steps.

### [`step2_analysis.html`](./step2_analysis.html)

**Statistical Modeling: Case-Crossover and DiD**

* Implements a stratified case-crossover design to control for time-invariant confounding.
* Applies Differences-in-Differences (DiD) models clustered by exposure windows.
* Uses Synthetic Control Methods (SCM) to build counterfactual trajectories for high-speed collisions.

### [`step3_analysis_part_2.html`](./step3_analysis_part_2.html)

**Causal Inference Using Time-GPT and Google's CausalImpact package**

* Applies time-series counterfactual modeling using Time-GPT (a transformer-based model for temporal causal inference).
* Estimates the causal impact using a Bayesian time series analysis of the F1 event across different years and windows.
