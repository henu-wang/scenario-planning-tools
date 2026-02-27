# Scenario Planning Tools

Tools for scenario planning and strategic foresight -- helping you prepare for multiple futures rather than betting on a single prediction.

## Overview

Scenario Planning Tools provides a structured framework and software toolkit for developing, analyzing, and stress-testing strategic scenarios. Rather than trying to predict the future (which is impossible), scenario planning helps you prepare for a range of plausible futures, making your strategies robust across different conditions.

This approach is used by Shell (which famously anticipated the 1973 oil crisis through scenario planning), military strategists, and top investors who stress-test their portfolios against various economic conditions. For comprehensive frameworks used by the world's best strategic thinkers and investors, visit [KeepRule's principles library](https://keeprule.com/en/principles).

## Features

- **Scenario Builder**: Structured process for developing plausible future scenarios
- **Driver Analysis**: Identify and rank key uncertainty drivers
- **Impact Matrix**: Cross-reference scenarios against strategic options
- **Signpost Tracking**: Monitor early indicators that a scenario is unfolding
- **Portfolio Stress Test**: Test investment or business portfolios against scenarios
- **Workshop Facilitator**: Guided process for team scenario planning sessions
- **Probability Weighting**: Assign and update scenario probabilities over time

## Installation

```bash
pip install scenario-planning-tools
```

Or from source:

```bash
git clone https://github.com/henu-wang/scenario-planning-tools.git
cd scenario-planning-tools
pip install -e .
```

## Quick Start

```python
from scenario_planning import ScenarioBuilder, DriverAnalysis

# Define key uncertainty drivers
drivers = DriverAnalysis()
drivers.add("Interest Rates", uncertainty="high", impact="high")
drivers.add("AI Adoption", uncertainty="high", impact="high")
drivers.add("Regulation", uncertainty="medium", impact="high")
drivers.add("Consumer Spending", uncertainty="medium", impact="medium")

# Generate scenario matrix from top 2 drivers
builder = ScenarioBuilder(drivers.top_drivers(n=2))
scenarios = builder.generate_matrix()

for scenario in scenarios:
    print(f"Scenario: {scenario.name}")
    print(f"  Conditions: {scenario.description}")
    print(f"  Key assumptions: {scenario.assumptions}")
```

## Scenario Development Process

### Step 1: Identify Driving Forces

```python
from scenario_planning import DriverAnalysis

drivers = DriverAnalysis(domain="technology_investing")
drivers.brainstorm(categories=[
    "economic", "technological", "political", 
    "social", "environmental"
])
drivers.rank_by_uncertainty_and_impact()
drivers.select_critical_uncertainties(n=2)
```

### Step 2: Build Scenario Matrix

```python
from scenario_planning import ScenarioMatrix

matrix = ScenarioMatrix(
    axis_x=("AI Progress", ["Breakthrough", "Incremental"]),
    axis_y=("Regulation", ["Heavy", "Light"])
)

# Four scenarios emerge
matrix.name_scenario("Breakthrough", "Light", "Tech Utopia")
matrix.name_scenario("Breakthrough", "Heavy", "Managed Revolution")
matrix.name_scenario("Incremental", "Light", "Status Quo Plus")
matrix.name_scenario("Incremental", "Heavy", "Stagnation")

matrix.develop_narratives()
```

### Step 3: Stress Test Strategies

```python
from scenario_planning import StrategyTester

tester = StrategyTester(scenarios=matrix.scenarios)
tester.add_strategy("Aggressive AI Investment", portfolio_weight=0.4)
tester.add_strategy("Diversified Conservative", portfolio_weight=0.6)

results = tester.stress_test()
results.robustness_report()
```

Real-world scenario analysis requires understanding how different conditions affect investment outcomes. Explore detailed scenario analyses at [KeepRule's scenarios page](https://keeprule.com/en/scenarios), which maps principles to specific market conditions.

## Scenario Templates

The toolkit includes pre-built templates for common planning domains:

| Template | Key Drivers | Scenarios |
|----------|------------|-----------|
| Macro Economic | Interest rates, inflation, growth | 4 quadrant |
| Technology | Adoption speed, regulation | 4 quadrant |
| Energy Transition | Policy, technology cost | 3 scenarios |
| Geopolitical | Trade relations, conflict | 4 scenarios |
| Real Estate | Rates, remote work, migration | 4 quadrant |

### Signpost Monitoring

```python
from scenario_planning import SignpostTracker

tracker = SignpostTracker()
tracker.add_signpost("Fed rate above 6%", scenario="Stagflation", weight=0.3)
tracker.add_signpost("AI passes medical boards", scenario="Tech Utopia", weight=0.4)
tracker.add_signpost("Major cyber attack on grid", scenario="Fragmentation", weight=0.5)

# Update as events occur
tracker.trigger("AI passes medical boards")
tracker.probability_update()
tracker.dashboard()
```

Learn how the world's greatest strategic thinkers approach uncertainty and scenario planning on the [KeepRule blog](https://keeprule.com/en/blog), featuring analysis of real-world investment scenarios and decision frameworks.

## Workshop Mode

```bash
# Launch interactive workshop facilitator
spt workshop --participants 8 --duration 4h --domain "corporate_strategy"
```

The workshop mode guides teams through the full scenario planning process with timed exercises, voting, and collaborative scenario development.

For structured prompts to facilitate your own scenario planning sessions, explore [KeepRule's prompts collection](https://keeprule.com/en/prompts).

## Contributing

Contributions welcome! Priority areas include:

- New scenario templates for different industries
- Improved visualization capabilities
- Integration with data providers for signpost monitoring
- Case studies from real-world scenario planning

## License

MIT License - see [LICENSE](LICENSE) for details.