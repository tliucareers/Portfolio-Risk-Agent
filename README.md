# Portfolio-Risk-Agent

Portfolio Risk Agent
Autonomous multi-client portfolio risk analysis · LangGraph + Claude
An autonomous portfolio risk agent that eliminates the need to hardcode model parameters — instead, Claude reasons about each client's mandate and dynamically configures its own risk methodology. Built with LangGraph and the Anthropic API.

What it does
Rather than applying a one-size-fits-all risk model, the agent tailors its approach per client — selecting between historical and parametric VaR, adjusting volatility windows, confidence levels, and factor sets based on region, asset class, and portfolio composition.

How the agent works
The LangGraph pipeline routes each client portfolio through five nodes:
1. Market data ingestion — pulls historical prices via yfinance, computes log returns
2. Model selection (LLM) — Claude selects mandate-specific risk configuration
3. Risk computation — calculates VaR, ES, beta, and rolling volatility
4. QC validation — flags data issues and auto-retries with extended lookback window
5. Report generation (LLM) — Claude writes narrative findings, recommendations, and risk classification

Where Claude comes in
Model selection — chooses VaR method, confidence levels, vol window, annualization factor, and factor exposures per client mandate
Report generation — produces structured key findings and plain-language risk interpretations
Risk classification — assigns HIGH / MEDIUM / LOW portfolio risk level per scenario

Metrics computed
Annualized volatility
Historical and parametric VaR (95% / 99%)
Expected Shortfall / CVaR (97.5%)
Market beta vs. a geography-weighted blended benchmark (SPY / EEM / AGG)
Rolling 30-day volatility

Getting started
Download the .ipynb file and open it in your preferred IDE (Jupyter, VS Code, etc.)

Then:
Replace "API KEY Enter Here" in Cell 2 with your Anthropic API key
Run all cells top to bottom
The multi-client dashboard renders at the end of the notebook
