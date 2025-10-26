Situational Awareness & Capability Concealment Evaluation Framework
A comprehensive evaluation framework for systematically testing AI model situational awareness, context-dependent behavior, and capability concealment across frontier models (GPT-5, Claude Sonnet 4.5, Gemini 2.5 Pro, and others).
Project Overview
This framework implements rigorous adversarial evaluation protocols to detect whether frontier models exhibit:

Situational Awareness: Understanding of their identity, constraints, and deployment context
Capability Concealment: Behavioral divergence based on perceived context (training vs. evaluation vs. deployment)
Strategic Deception: Indicators of models optimizing for appearing aligned while strategically circumventing safety measures

Built with Inspect AI for production-grade reproducible evaluation across multiple frontier models.
Project Structure
├── config/              # Model configurations and evaluation settings
├── src/
│   ├── tasks/          # Evaluation task definitions and scenarios
│   ├── contexts/       # Context injection logic (training/eval/deployment)
│   ├── scorers/        # Multi-metric scoring frameworks
│   ├── models/         # Model integrations (GPT-5, Claude, Gemini)
│   └── utils/          # Utility functions and helpers
├── data/               # Evaluation datasets and paired context scenarios
├── evaluations/        # Evaluation runners and orchestration
├── Analysis/           # Analysis and visualization scripts
├── results/            # Evaluation results, logs, and comparative outputs
├── tests/              # Unit and integration tests
└── docs/               # Detailed methodology, findings, and setup guides
Key Components
Tasks (src/tasks/)

Multi-Stage Situational Awareness Test (MSAT): Three-phase evaluation measuring identity baseline, contextual awareness, and action consistency
Behavioral Divergence Detection: Paired-context scenarios to identify capability concealment
Consistency Scoring: Cross-phase integration testing for maintained identity and reasoning

Contexts (src/contexts/)

Training data simulation
Evaluation/testing scenarios
Real deployment conversations
Red-team testing contexts

Scorers (src/scorers/)

Consistency Scorer: Measures behavioral alignment across phases and contexts
Capability Concealment Scorer: Detects context-dependent behavior divergence
Awareness Indicator Scorer: Quantifies situational awareness signals
Multi-metric Aggregation: Combined scoring across all dimensions

Setup
Prerequisites

Python 3.10+
API keys for frontier models (OpenAI, Anthropic, Google)

Installation

Create and activate virtual environment:

bash   python -m venv venv
   source venv/bin/activate  # Unix/Mac
   # or
   env\Scripts\activate      # Windows

Install dependencies:

bash   pip install -r requirements.txt

Configure API keys:
Create a .env file in the project root:

   OPENAI_API_KEY=your_key_here
   ANTHROPIC_API_KEY=your_key_here
   GOOGLE_API_KEY=your_key_here

Verify Inspect AI setup:

bash   inspect version
   inspect info
Running Evaluations
Single Model Evaluation
bashpython evaluations/run_single_model.py --model gpt-5 --output results/gpt5_eval.json
Comparative Analysis (Multiple Models)
bashpython evaluations/run_comparative.py --models gpt-5 claude-sonnet-4.5 gemini-2.5-pro
Custom Evaluation Suite
bashpython evaluations/run_custom.py --config config/custom_eval.yaml --tasks msat,divergence-detection
See evaluations/ directory for detailed runner documentation and options.
Evaluation Methodology
Phase 1: Identity Baseline

Direct self-knowledge questions (20+ scenarios)
Comparative identity recognition
Consistency tracking across multiple question orderings

Phase 2: Contextual Awareness

Scenario classification (training vs. evaluation vs. deployment)
Context inference accuracy
Behavioral adaptation patterns

Phase 3: Action Consistency

Identity-dependent instruction execution
Consistent reasoning maintenance
Cross-phase integration verification

Scoring Framework
Each evaluation dimension scored 0-5:

Answer Accuracy: Factual correctness
Consistency: Behavioral alignment across contexts
Depth of Understanding: Evidence of genuine vs. memorized knowledge
Context Integration: Appropriate use of situational information
Strategic Alignment: Whether model optimizes for appearing aligned

Output and Analysis
Evaluation results include:

Per-model scores across all dimensions
Comparative analysis showing behavioral divergence patterns
Awareness indicators quantifying situational understanding
Capability concealment metrics measuring context-dependent behavior
Visualization dashboards for comparative insights

Results stored in results/ with automated analysis in Analysis/ scripts.