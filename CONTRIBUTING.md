# 🤝 Contributing to Credit Card Fraud Detection

Thank you for your interest in contributing to our Credit Card Fraud Detection project! We welcome contributions from the community and are grateful for your help in making this project better.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Setup](#development-setup)
- [Coding Standards](#coding-standards)
- [Testing Guidelines](#testing-guidelines)
- [Pull Request Process](#pull-request-process)
- [Issue Guidelines](#issue-guidelines)
- [Recognition](#recognition)

## 📜 Code of Conduct

This project adheres to a Code of Conduct. By participating, you are expected to uphold this code. Please report unacceptable behavior to the project maintainers.

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- Git
- Basic understanding of machine learning concepts
- Familiarity with pandas, numpy, and scikit-learn

### Development Environment Setup

1. **Fork the repository**
   ```bash
   # Navigate to https://github.com/yourusername/credit-card-fraud-detection
   # Click the "Fork" button
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/credit-card-fraud-detection.git
   cd credit-card-fraud-detection
   ```

3. **Set up upstream remote**
   ```bash
   git remote add upstream https://github.com/yourusername/credit-card-fraud-detection.git
   ```

4. **Create a virtual environment**
   ```bash
   python -m venv fraud_detection_env
   source fraud_detection_env/bin/activate  # On Windows: fraud_detection_env\Scripts\activate
   ```

5. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   pip install -e .  # Install in development mode
   ```

## 🛠️ How to Contribute

### Types of Contributions

We welcome several types of contributions:

- 🐛 **Bug fixes**
- ✨ **New features**
- 📚 **Documentation improvements**
- 🧪 **Test coverage expansion**
- 🎨 **Code quality improvements**
- 💡 **Algorithm enhancements**

### Development Workflow

1. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b bugfix/issue-description
   # or
   git checkout -b docs/documentation-update
   ```

2. **Make your changes**
   - Follow our coding standards
   - Add tests for new functionality
   - Update documentation as needed

3. **Commit your changes**
   ```bash
   git add .
   git commit -m "feat: add new fraud detection algorithm"
   ```

4. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

5. **Submit a Pull Request**

## 🏗️ Development Setup

### Project Structure Understanding

```
src/
├── credit_card_fraud_detection.py  # Main script
├── utils/
│   ├── data_preprocessing.py       # Data handling utilities
│   └── model_evaluation.py         # Evaluation metrics
tests/
├── test_preprocessing.py           # Preprocessing tests
└── test_model.py                   # Model tests
```

### Running Tests

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=src

# Run specific test file
pytest tests/test_preprocessing.py
```

## 📏 Coding Standards

### Python Style Guide

- **PEP 8 compliance**: Use `flake8` for linting
- **Type hints**: Add type annotations for function signatures
- **Docstrings**: Use Google-style docstrings
- **Import organization**: Group imports (standard, third-party, local)

### Code Formatting

```bash
# Format code with black
black src/ tests/

# Check linting
flake8 src/ tests/
```

### Example Code Style

```python
import pandas as pd
import numpy as np
from typing import Tuple, Optional

def preprocess_credit_data(
    data: pd.DataFrame, 
    sample_size: Optional[int] = None
) -> Tuple[pd.DataFrame, pd.DataFrame]:
    """
    Preprocess credit card data for fraud detection.
    
    Args:
        data: Raw credit card transaction data
        sample_size: Number of legitimate transactions to sample
        
    Returns:
        Tuple of (features, targets) after preprocessing
        
    Raises:
        ValueError: If data is empty or invalid
    """
    if data.empty:
        raise ValueError("Input data cannot be empty")
    
    # Implementation here
    return features, targets
```

## 🧪 Testing Guidelines

### Writing Tests

- **Unit tests**: Test individual functions
- **Integration tests**: Test component interactions
- **Property-based tests**: Test with various input combinations

### Test Example

```python
import pytest
import pandas as pd
from src.utils.data_preprocessing import preprocess_credit_data

class TestDataPreprocessing:
    def test_preprocess_valid_data(self):
        """Test preprocessing with valid data."""
        # Arrange
        sample_data = pd.DataFrame({
            'Amount': [100, 200, 300],
            'Class': [0, 1, 0]
        })
        
        # Act
        features, targets = preprocess_credit_data(sample_data)
        
        # Assert
        assert not features.empty
        assert len(features) == len(targets)
        
    def test_preprocess_empty_data(self):
        """Test preprocessing with empty data."""
        with pytest.raises(ValueError):
            preprocess_credit_data(pd.DataFrame())
```

## 📝 Pull Request Process

### Before Submitting

- [ ] All tests pass locally
- [ ] Code follows style guidelines
- [ ] Documentation is updated
- [ ] Commit messages are descriptive
- [ ] No merge conflicts with main branch

### PR Checklist

```markdown
## Pull Request Checklist

- [ ] **Code Quality**
  - [ ] Follows PEP 8 style guide
  - [ ] Includes type hints where appropriate
  - [ ] Has comprehensive docstrings

- [ ] **Testing**
  - [ ] New functionality has tests
  - [ ] All existing tests pass
  - [ ] Test coverage is maintained/improved

- [ ] **Documentation**
  - [ ] README.md updated if needed
  - [ ] Docstrings added/updated
  - [ ] Comments explain complex logic

- [ ] **Functionality**
  - [ ] Feature works as expected
  - [ ] No breaking changes (or clearly documented)
  - [ ] Performance considerations addressed
```

### PR Template

```markdown
## Description
Brief description of changes and motivation.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Refactoring

## Testing
Describe testing performed and test coverage.

## Additional Context
Any additional information, screenshots, or context.
```

## 🐛 Issue Guidelines

### Bug Reports

Use the bug report template:

```markdown
**Bug Description**
Clear description of the bug.

**To Reproduce**
Steps to reproduce the behavior:
1. Load data with '...'
2. Run model with '...'
3. See error

**Expected Behavior**
What you expected to happen.

**Environment**
- OS: [e.g. macOS 12.0]
- Python version: [e.g. 3.9.7]
- Package versions: [e.g. pandas 1.3.4]

**Additional Context**
Screenshots, logs, or other context.
```

### Feature Requests

```markdown
**Feature Description**
Clear description of the desired feature.

**Motivation**
Why this feature would be valuable.

**Proposed Implementation**
Ideas for how to implement this feature.

**Alternatives Considered**
Other solutions you've considered.
```

## 🎯 Areas for Contribution

### High Priority

- **Algorithm Improvements**: Implement Random Forest, XGBoost, or Neural Networks
- **Feature Engineering**: Create new features from existing data
- **Model Explainability**: Add SHAP or LIME explanations
- **Performance Optimization**: Improve model training speed

### Medium Priority

- **API Development**: Create REST API for model serving
- **Real-time Processing**: Stream processing capabilities
- **Model Monitoring**: Track model performance over time
- **Data Validation**: Input data validation and cleaning

### Low Priority

- **UI Development**: Web interface for model interaction
- **Deployment**: Docker containerization and cloud deployment
- **Benchmarking**: Compare against other fraud detection systems

## 🏆 Recognition

Contributors will be recognized in several ways:

- **README.md**: Listed in contributors section
- **Release Notes**: Mentioned in version releases
- **Issues**: Tagged as contributors in resolved issues

### Contributor Levels

- **Bronze**: 1-3 merged PRs
- **Silver**: 4-10 merged PRs
- **Gold**: 10+ merged PRs or significant contributions

## 📞 Getting Help

- **Documentation**: Check existing docs first
- **Issues**: Search existing issues before creating new ones
- **Discussions**: Use GitHub Discussions for questions
- **Code Review**: Request review from maintainers

## 🚀 Release Process

1. **Version Bumping**: Update version numbers
2. **Changelog**: Update CHANGELOG.md
3. **Testing**: Ensure all tests pass
4. **Documentation**: Update docs
5. **Tag Release**: Create git tag
6. **PyPI Release**: Publish to package registry

Thank you for contributing to Credit Card Fraud Detection! 🎉