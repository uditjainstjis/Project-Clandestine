# Project Clandestine: AI Information Verification System

## 🎯 Project Overview

**Mission**: Building a comprehensive AI information verification system to combat the growing issue of AI-generated misinformation polluting the web and creating feedback loops of false information.

### The Problem
AI is slowly poisoning its own well. With 1200+ AI-generated content sites and a dangerous feedback loop where:
1. AI/LLM gives wrong info →
2. Someone publishes that info on reputed sites →
3. Content gets views and engagement →
4. Next AI models see high-engagement content as "must be true" →
5. Misinformation becomes a trusted source → cycle repeats

### Our Solution
A verification system that doesn't just fetch information but actively verifies and proves it through trusted sources and cross-referencing.

## 🏗️ System Architecture

### Core Flow
```
User prompt → Router (classifier) → Crawler → Knowledge Base → LLM (summarizer)
```

### Key Components

#### 1. Parameter Selection System
- Define what we consider "correct" (research papers, authoritative sources)
- Domain-specific parameter selection
- Dynamic trust scoring for sources

#### 2. Verification Pipeline
- **Option A**: Use Perplexity API → scrape research papers → LLM parsing
- **Option B**: Custom search → LLM-generated search queries → web scraping → relevance filtering

#### 3. Trust Scoring Algorithm

**Dynamic Trust Score (0-1 scale)**

| Factor | Description | Scoring Rule |
|--------|-------------|-------------|
| Domain Reputation | Authority level | 0.9 for .edu/.gov; 0.8 for .org |
| Source Verification | Cross-citations | +0.05 per citation |
| Fact-Check Record | Misinformation history | -0.2 for false reports |
| Recency | Data freshness | -0.1 for >2 years old |
| Consistency | Cross-source matching | +0.2 for high similarity |

**Final Score Calculation:**
```
FinalScore = 0.4D + 0.3C + 0.2R + 0.1F
```
Where: D=Domain trust, C=Cross-source consistency, R=Recency, F=Fact-check verification

**Trust Levels:**
- ≥0.75: "Trusted"
- 0.5-0.75: "Partially Trusted"
- <0.5: "Untrusted"

#### 4. Cross-Verification System
- Search 3-5 trusted sources for same claim
- Compare entities, dates, numbers
- Use NLP techniques (BERT embeddings, RoBERTa-large-mnli)
- Textual entailment analysis

## 📊 Example Verification Flow

**User Query**: "NASA confirms alien life on Mars."

1. **Router**: Classifies as "Science News"
2. **Crawler**: Searches NASA, Reuters, BBC Science
3. **Knowledge Base**: No official NASA report found
4. **Cross-check**: Reuters/BBC report "No official confirmation"
5. **Fact-check API**: Snopes lists as false
6. **Result**: Trust score = 0.18 → **FAKE**

## 🎯 Precision vs Recall Strategy

### High Precision (Minimize False Positives)
- When false alarms cause serious harm
- Examples: Reputation damage, legal action, wrongful content takedown

### High Recall (Minimize False Negatives)
- When missing real issues is dangerous
- Examples: Health misinformation, safety-critical information

## 🌐 Blue Tick User System
- Verified trustworthy users across the internet
- Training data based on their contributions
- Continuous knowledge base refinement

## 🔗 Supporting Evidence

### Academic Research on AI Content Pollution
- [ScienceDirect - Domain General Cognitive Ability](https://www.sciencedirect.com/topics/psychology/domain-general-cognitive-ability)
- [ScienceDirect - Research Article](https://www.sciencedirect.com/science/article/abs/pii/S1364661312000824)
- [PhD Discussion Thread](https://bsky.app/profile/irisvanrooij.bsky.social/post/3lvm7x4oo2k2o)

### Open Letters from Academia
- [1100+ Professor Signatures - Stop Uncritical AI Adoption in Academia](https://openletter.earth/open-letter-stop-the-uncritical-adoption-of-ai-technologies-in-academia-b65bba1e)
- [Educators Against GenAI in Education](https://openletter.earth/an-open-letter-from-educators-who-refuse-the-call-to-adopt-genai-in-education-cb4aee75)

### Related Video
- [AI Information Problem Explanation](https://www.youtube.com/watch?v=_zfN9wnPvU0)

## 👥 Team & Responsibilities

### Current Team
- **Udit**: Research Lead - Core problem analysis and solution design
- **Divya**: Research - Trust scoring and verification algorithms
- **Rishik**: Research - Cross-verification and NLP implementation

## 📁 Repository Structure

```
/
├── README.md                    # This file
├── docs/                        # Documentation
│   ├── api-reference.md        # API documentation
│   ├── architecture.md         # System architecture details
│   ├── contributing.md         # Contribution guidelines
│   └── use-cases.md            # Detailed use cases
├── research/                    # Research materials
│   ├── papers/                 # Academic papers and references
│   ├── experiments/            # Research experiments
│   └── findings/               # Research findings and notes
├── src/                         # Source code
│   ├── crawler/                # Web crawling modules
│   ├── classifier/             # Content classification
│   ├── verifier/               # Verification engine
│   └── api/                    # API endpoints
├── daily-progress/             # Daily progress tracking
│   ├── templates/              # Log templates
│   └── logs/                   # Individual daily logs
└── tests/                      # Test suites
    ├── unit/                   # Unit tests
    └── integration/            # Integration tests
```

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Node.js 16+
- Docker (optional)

### Installation
```bash
git clone https://github.com/uditjainstjis/Project-Clandestine.git
cd Project-Clandestine
pip install -r requirements.txt
```

### Quick Start
```bash
# Run the verification system
python src/main.py --query "your query here"

# Start development server
npm run dev
```

## 📈 Progress Tracking

### Phase 1: Research & Foundation (Current)
- [x] Problem identification and analysis
- [x] Core architecture design
- [x] Trust scoring algorithm design
- [ ] Initial prototype development

### Phase 2: Development
- [ ] Core verification engine
- [ ] API development
- [ ] Web interface
- [ ] Testing suite

### Phase 3: Enhancement
- [ ] Advanced NLP integration
- [ ] Real-time verification
- [ ] Browser extension
- [ ] Mobile app

## 🤝 Contributing

See [CONTRIBUTING.md](docs/contributing.md) for detailed contribution guidelines.

### Daily Progress Logging
All team members should log daily progress in `daily-progress/logs/YYYY-MM-DD-[name].md`

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🔮 Future Vision

Building the next generation of information verification - a system that doesn't just compete with Perplexity but sets the standard for verified, trustworthy AI-powered information retrieval.

---

**Note**: This is an active research project. The system is currently in the research and development phase. Contributions and feedback are welcome!
