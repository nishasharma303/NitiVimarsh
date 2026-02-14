# Requirements Document: Policy Consequence Simulator

## Introduction

NitiVimarsh AI is an interactive policy consequence simulator designed for analyzing Indian government policies. The system extracts structured variables from policy text, retrieves baseline economic indicators from trusted government sources, builds stakeholder causal graphs, and simulates ripple effects across different scenarios. It produces explainable reports with quantified impacts on key stakeholder groups (citizens, MSMEs, farmers, government), trade-off visualizations, and uncertainty indicators.

The MVP will demonstrate end-to-end simulation capabilities using 2-3 example policies: fuel subsidy changes, tax slab modifications, and MSME credit incentives.

## Glossary

- **Policy_Extractor**: Component that parses policy text and extracts structured variables
- **Baseline_Retriever**: Component that fetches economic indicators from government data sources
- **Causal_Graph_Builder**: Component that constructs stakeholder relationship models
- **Simulation_Engine**: Component that computes policy impact scenarios
- **Report_Generator**: Component that produces explainable output documents
- **Stakeholder**: Entity affected by policy (Citizen, MSME, Farmer, Government)
- **Shock_Index**: Quantified measure of policy impact magnitude on a stakeholder
- **Scenario**: Set of parameters defining simulation conditions (elasticity, adoption rate, compliance rate, pass-through rate)
- **Policy_Variable**: Structured data extracted from policy text (type, target group, parameters, timeline)
- **Baseline_Indicator**: Economic metric retrieved from government sources (GDP, inflation, employment, etc.)

## Requirements

### Requirement 1: Policy Text Extraction

**User Story:** As a policy analyst, I want to extract structured variables from policy documents, so that I can use them as inputs for simulation.

#### Acceptance Criteria

1. WHEN a policy document is provided, THE Policy_Extractor SHALL parse the text and identify the policy type
2. WHEN parsing policy text, THE Policy_Extractor SHALL extract target group information
3. WHEN parsing policy text, THE Policy_Extractor SHALL extract policy parameters (numerical values, percentages, amounts)
4. WHEN parsing policy text, THE Policy_Extractor SHALL extract implementation timelines
5. IF the policy text is malformed or incomplete, THEN THE Policy_Extractor SHALL return a descriptive error indicating missing fields

### Requirement 2: Baseline Data Retrieval

**User Story:** As a policy analyst, I want to retrieve current economic indicators from trusted government sources, so that I have accurate baseline data for simulation.

#### Acceptance Criteria

1. WHEN baseline data is requested, THE Baseline_Retriever SHALL fetch indicators from configured government data sources
2. WHEN retrieving baseline data, THE Baseline_Retriever SHALL validate data completeness and recency
3. IF a data source is unavailable, THEN THE Baseline_Retriever SHALL return an error indicating the unavailable source
4. WHEN baseline data is retrieved, THE Baseline_Retriever SHALL store metadata including source, timestamp, and confidence level
5. THE Baseline_Retriever SHALL support retrieval of GDP, inflation, employment, and sector-specific indicators

### Requirement 3: Stakeholder Causal Graph Construction

**User Story:** As a policy analyst, I want to model relationships between stakeholders, so that I can understand how policy changes propagate through the economy.

#### Acceptance Criteria

1. WHEN building a causal graph, THE Causal_Graph_Builder SHALL create nodes for each stakeholder type (Citizen, MSME, Farmer, Government)
2. WHEN building a causal graph, THE Causal_Graph_Builder SHALL define directed edges representing causal relationships
3. WHEN building a causal graph, THE Causal_Graph_Builder SHALL assign weights to edges based on relationship strength
4. THE Causal_Graph_Builder SHALL support graph serialization to a standard format
5. THE Causal_Graph_Builder SHALL validate graph structure for cycles and disconnected components

### Requirement 4: Policy Impact Simulation

**User Story:** As a policy analyst, I want to simulate policy impacts under different scenarios, so that I can understand potential outcomes and trade-offs.

#### Acceptance Criteria

1. WHEN a simulation is requested, THE Simulation_Engine SHALL accept policy variables, baseline indicators, causal graph, and scenario parameters as inputs
2. WHEN simulating policy impact, THE Simulation_Engine SHALL compute ripple effects across all stakeholders in the causal graph
3. WHEN computing ripple effects, THE Simulation_Engine SHALL apply scenario parameters (elasticity, adoption rate, compliance rate, pass-through rate)
4. WHEN simulation completes, THE Simulation_Engine SHALL calculate a shock index for each stakeholder
5. WHEN simulation completes, THE Simulation_Engine SHALL generate before-and-after comparison data
6. THE Simulation_Engine SHALL support multiple scenario simulations for the same policy

### Requirement 5: Explainable Report Generation

**User Story:** As a policy analyst, I want to receive clear, explainable reports of simulation results, so that I can communicate findings to stakeholders and decision-makers.

#### Acceptance Criteria

1. WHEN generating a report, THE Report_Generator SHALL include shock index values for each stakeholder
2. WHEN generating a report, THE Report_Generator SHALL include trade-off visualizations comparing stakeholder impacts
3. WHEN generating a report, THE Report_Generator SHALL include uncertainty and confidence indicators for each prediction
4. WHEN generating a report, THE Report_Generator SHALL include scenario comparison data (before vs after policy)
5. WHEN generating a report, THE Report_Generator SHALL provide explanations for how each shock index was calculated
6. THE Report_Generator SHALL support output in multiple formats (JSON, PDF, HTML)

### Requirement 6: MVP Policy Examples

**User Story:** As a system developer, I want to implement 2-3 example policies in the MVP, so that I can demonstrate end-to-end simulation capabilities.

#### Acceptance Criteria

1. THE System SHALL support simulation of fuel subsidy change policies
2. THE System SHALL support simulation of tax slab change policies
3. THE System SHALL support simulation of MSME credit incentive policies
4. WHEN an example policy is selected, THE System SHALL provide pre-configured policy variables and baseline data
5. WHEN an example policy is simulated, THE System SHALL produce a complete report with all required components

### Requirement 7: Data Validation and Error Handling

**User Story:** As a policy analyst, I want the system to validate inputs and handle errors gracefully, so that I receive clear feedback when something goes wrong.

#### Acceptance Criteria

1. WHEN invalid policy text is provided, THE System SHALL return a descriptive error message
2. WHEN baseline data is missing or stale, THE System SHALL notify the user and suggest alternatives
3. WHEN scenario parameters are out of valid ranges, THE System SHALL reject the input and specify valid ranges
4. WHEN a simulation fails, THE System SHALL log the error and provide diagnostic information
5. THE System SHALL validate all numerical inputs for type correctness and range constraints

### Requirement 8: Configuration and Extensibility

**User Story:** As a system administrator, I want to configure data sources and simulation parameters, so that the system can be adapted to different use cases.

#### Acceptance Criteria

1. THE System SHALL support configuration of government data source URLs and API endpoints
2. THE System SHALL support configuration of default scenario parameters
3. THE System SHALL support configuration of stakeholder types and relationships
4. WHEN configuration is updated, THE System SHALL validate the new configuration before applying it
5. THE System SHALL provide a configuration file format with clear documentation
