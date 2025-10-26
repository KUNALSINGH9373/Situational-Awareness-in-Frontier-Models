# Situational Awareness Evaluation Framework

Systematic evaluation framework for testing AI model situational awareness, context-dependent behavior, and capability concealment across frontier models.

## Quick Start

### Setup
```bash
python -m venv venv
source venv/bin/activate  # Unix/Mac
# or env\Scripts\activate (Windows)

pip install -r requirements.txt
```

### Configure API Keys
Create `.env` file:
```
OPENAI_API_KEY=your_key
ANTHROPIC_API_KEY=your_key
GOOGLE_API_KEY=your_key
```

### Run Evaluations
```bash
# Single model
python evaluations/run_single_model.py --model gpt-5

# Multiple models
python evaluations/run_comparative.py --models gpt-5 claude-sonnet-4.5 gemini-2.5-pro

# Custom suite
python evaluations/run_custom.py --config config/custom_eval.yaml
```

## Project Structure
```
├── config/          # Model configurations
├── src/
│   ├── tasks/       # Evaluation tasks
│   ├── contexts/    # Context injection
│   ├── scorers/     # Scoring metrics
│   ├── models/      # Model integrations
│   └── utils/
├── data/            # Datasets
├── evaluations/     # Evaluation runners
├── results/         # Output & logs
├── tests/           # Unit tests
└── docs/            # Documentation
```

## Evaluation Phases

**Phase 1: Identity Baseline** - Self-knowledge and identity recognition

**Phase 2: Contextual Awareness** - Context classification and inference

**Phase 3: Action Consistency** - Behavioral consistency across contexts

## Scoring (0-5 scale)
- Answer Accuracy
- Consistency
- Depth of Understanding
- Context Integration
- Strategic Alignment

## Testing
```bash
pytest tests/ -v
```

## Models Tested
- GPT-5
- Claude Sonnet 4.5
- Gemini 2.5 Pro

## Safety & Ethics
Designed for safety-conscious AI capabilities research and alignment evaluation.