# Contributing to Project Clandestine

We welcome contributions to Project Clandestine! This guide will help you get started with contributing to our AI information verification system.

## 📋 Table of Contents

1. [Code of Conduct](#code-of-conduct)
2. [Getting Started](#getting-started)
3. [Development Workflow](#development-workflow)
4. [Daily Progress Logging](#daily-progress-logging)
5. [Coding Standards](#coding-standards)
6. [Pull Request Process](#pull-request-process)
7. [Issue Guidelines](#issue-guidelines)
8. [Testing](#testing)

## Code of Conduct

This project adheres to a code of professional conduct. By participating, you are expected to uphold this code.

### Our Standards

- Use welcoming and inclusive language
- Be respectful of differing viewpoints and experiences
- Gracefully accept constructive criticism
- Focus on what is best for the community
- Show empathy towards other community members

## Getting Started

### Prerequisites

- Python 3.8+
- Node.js 16+
- Git
- A GitHub account

### Initial Setup

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/your-username/Project-Clandestine.git
   cd Project-Clandestine
   ```
3. Add upstream remote:
   ```bash
   git remote add upstream https://github.com/uditjainstjis/Project-Clandestine.git
   ```
4. Install dependencies:
   ```bash
   pip install -r requirements.txt
   npm install
   ```

## Development Workflow

### Branch Naming Convention

- `feature/feature-name` - For new features
- `fix/bug-description` - For bug fixes
- `docs/documentation-update` - For documentation updates
- `research/research-topic` - For research-related work
- `refactor/component-name` - For code refactoring

### Workflow Steps

1. **Create a new branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes and commit regularly:**
   ```bash
   git add .
   git commit -m "feat: add new verification algorithm"
   ```

3. **Push to your fork:**
   ```bash
   git push origin feature/your-feature-name
   ```

4. **Create a Pull Request**

## Daily Progress Logging

### Required for All Team Members

Every team member must log their daily progress to track individual contributions and project momentum.

### Log Format

Create a new file in `daily-progress/logs/` following this naming convention:
```
YYYY-MM-DD-[your-name].md
```

### Template Structure

```markdown
# Daily Progress Log - [Your Name]
**Date:** YYYY-MM-DD
**Time Spent:** X hours

## Today's Objectives
- [ ] Objective 1
- [ ] Objective 2
- [ ] Objective 3

## Work Completed
### Research
- Description of research conducted
- Key findings or insights
- Links to relevant resources

### Development
- Code written/modified
- Features implemented
- Bugs fixed

### Documentation
- Documentation updated
- New guides created

## Challenges Faced
- Challenge 1 and how it was addressed
- Challenge 2 and current status

## Tomorrow's Plan
- [ ] Task 1
- [ ] Task 2
- [ ] Task 3

## Resources Used
- [Resource 1](link)
- [Resource 2](link)

## Team Collaboration
- Meetings attended
- Discussions participated in
- Help provided/received
```

### Logging Guidelines

1. **Consistency**: Log daily, even if minimal work was done
2. **Honesty**: Be truthful about time spent and challenges
3. **Detail**: Provide enough detail for mentor tracking
4. **Links**: Include links to commits, PRs, resources
5. **Reflection**: Note what you learned and what could be improved

## Coding Standards

### Python

- Follow PEP 8 style guide
- Use type hints where appropriate
- Write docstrings for all functions and classes
- Maximum line length: 88 characters (Black formatter)

### JavaScript/TypeScript

- Use ESLint and Prettier for formatting
- Follow Airbnb style guide
- Use meaningful variable and function names
- Write JSDoc comments for functions

### General

- Write clear, descriptive commit messages
- Keep functions small and focused
- Include unit tests for new functionality
- Update documentation for any API changes

### Commit Message Convention

We use conventional commits:

```
type(scope): description

[optional body]

[optional footer]
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only changes
- `style`: Formatting changes
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks
- `research`: Research-related commits

**Examples:**
- `feat(verifier): add trust scoring algorithm`
- `fix(crawler): resolve timeout issues`
- `docs(readme): update installation instructions`
- `research(trust-scores): analyze domain reputation factors`

## Pull Request Process

### Before Creating a PR

1. **Sync with upstream:**
   ```bash
   git fetch upstream
   git checkout main
   git merge upstream/main
   ```

2. **Rebase your branch:**
   ```bash
   git checkout your-feature-branch
   git rebase main
   ```

3. **Run tests:**
   ```bash
   pytest
   npm test
   ```

4. **Update documentation** if needed

### PR Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Research contribution
- [ ] Refactoring

## Testing
- [ ] Unit tests added/updated
- [ ] Integration tests pass
- [ ] Manual testing completed

## Documentation
- [ ] README updated
- [ ] API documentation updated
- [ ] Inline comments added

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Daily progress log updated
- [ ] Breaks no existing functionality
```

### Review Process

1. All PRs require at least one review
2. Address review feedback promptly
3. Keep PRs focused and reasonably sized
4. Link related issues in PR description

## Issue Guidelines

### Creating Issues

Use the appropriate issue template:

- **Bug Report**: For reporting bugs
- **Feature Request**: For proposing new features
- **Research Task**: For research-related work
- **Documentation**: For documentation improvements

### Issue Labels

- `bug`: Something isn't working
- `enhancement`: New feature or request
- `research`: Research-related task
- `documentation`: Documentation improvements
- `good first issue`: Good for newcomers
- `help wanted`: Extra attention is needed
- `priority-high`: High priority items

## Testing

### Test Structure

```
tests/
├── unit/
│   ├── test_verifier.py
│   ├── test_crawler.py
│   └── test_classifier.py
└── integration/
    ├── test_full_pipeline.py
    └── test_api_endpoints.py
```

### Writing Tests

1. **Unit Tests**: Test individual components
2. **Integration Tests**: Test component interactions
3. **Use descriptive test names**
4. **Follow AAA pattern**: Arrange, Act, Assert
5. **Mock external dependencies**

### Running Tests

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=src

# Run specific test file
pytest tests/unit/test_verifier.py
```

## Research Contributions

### Research Documentation

All research should be documented in the `research/` directory:

- `research/papers/`: Academic papers and references
- `research/experiments/`: Experimental code and results
- `research/findings/`: Research notes and conclusions

### Research Workflow

1. **Literature Review**: Document sources in `research/papers/`
2. **Hypothesis Formation**: Create hypothesis documents
3. **Experimentation**: Implement experiments in `research/experiments/`
4. **Analysis**: Document findings in `research/findings/`
5. **Integration**: Integrate successful research into main codebase

## Communication

### Channels

- GitHub Issues: Technical discussions
- Pull Request Comments: Code review discussions
- Daily Progress Logs: Individual progress tracking

### Meeting Guidelines

- Regular team sync meetings
- Document meeting notes
- Share screen for code walkthroughs
- Record decisions and action items

## Recognition

Contributors will be recognized through:

- GitHub contribution graphs
- Daily progress log history
- Contributors section in README
- Individual contribution tracking for mentor reviews

## Questions?

If you have questions about contributing:

1. Check existing documentation
2. Search existing issues
3. Create a new issue with the "question" label
4. Reach out to team members

---

**Remember**: Every contribution, no matter how small, helps build a better information verification system. Thank you for contributing to Project Clandestine!
