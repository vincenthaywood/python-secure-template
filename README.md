# Secure Python Template

A production-ready Python template with comprehensive security measures and CI/CD pipeline.

## 🛡️ Security Features

- ✅ **Automated vulnerability scanning** (Safety, Bandit, Snyk, CodeQL)
- ✅ **Security-focused linting** (Bandit security linter)
- ✅ **Dependency security checks** (pip-audit, Safety)
- ✅ **Pre-commit hooks** (automated security checks)
- ✅ **Daily security scans** (scheduled GitHub Actions)
- ✅ **Multi-Python version testing** (3.9, 3.10, 3.11, 3.12)

## 🚀 Quick Start

1. **Use this template** - Click "Use this template" button
2. **Clone your new repository**
3. **Create virtual environment**: 
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
4. **Install dependencies**: 
   ```bash
   pip install -r requirements.txt
   pip install -r requirements-dev.txt
   ```
5. **Install pre-commit hooks**: `pre-commit install`
6. **Optional**: Add `SNYK_TOKEN` to GitHub Secrets for enhanced scanning

## 📋 Available Commands

### Development
```bash
python -m venv venv          # Create virtual environment
source venv/bin/activate     # Activate virtual environment
pip install -r requirements-dev.txt  # Install dev dependencies
```

### Code Quality
```bash
black .                      # Format code
isort .                      # Sort imports
flake8 .                     # Lint code
mypy .                       # Type checking
```

### Security
```bash
bandit -r .                  # Security linting
safety check                 # Check dependencies for vulnerabilities
pip-audit                    # Comprehensive dependency audit
pre-commit run --all-files   # Run all pre-commit hooks
```

### Testing
```bash
pytest                       # Run tests
pytest --cov=.              # Run tests with coverage
pytest --cov=. --cov-report=html  # Generate HTML coverage report
```

## 🔧 Setup Instructions

### Required (for enhanced security):
1. **Enable GitHub Security Features**:
   - Go to Settings → Security & analysis
   - Enable Dependabot alerts
   - Enable Secret scanning

2. **Set Branch Protection**:
   - Go to Settings → Branches
   - Add rule for `main` branch
   - Require status checks: `security-scan`, `quality-checks`, `build`

### Optional (recommended):
1. **Add Snyk Token**:
   - Create account at https://app.snyk.io
   - Get API token from account settings
   - Add as `SNYK_TOKEN` in GitHub Secrets

## 🏗️ Template Structure

```
├── .github/workflows/       # CI/CD pipeline
├── .pre-commit-config.yaml  # Pre-commit hooks configuration
├── .flake8                  # Flake8 linting configuration
├── pyproject.toml           # Python project configuration
├── requirements.txt         # Production dependencies
├── requirements-dev.txt     # Development dependencies
├── src/                     # Source code
├── tests/                   # Test files
├── README.md                # This file
└── SECURITY.md              # Security documentation
```

## 🛡️ Security Pipeline

Every commit triggers:
1. **Security Scans** - Bandit, Safety, Snyk vulnerability detection
2. **Code Quality** - Black, isort, flake8, mypy
3. **Testing** - pytest with coverage
4. **Multi-version Testing** - Python 3.9, 3.10, 3.11, 3.12

## 📚 Documentation

See `SECURITY.md` for comprehensive security documentation and best practices.

## 🚀 Deployment

This template works with:
- ✅ Docker containers
- ✅ Cloud platforms (AWS, GCP, Azure)
- ✅ Serverless functions
- ✅ Traditional Python hosting

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run security checks: `pre-commit run --all-files`
5. Submit a pull request

---

**Note**: This template includes enterprise-grade security measures. All security checks must pass before deployment.
