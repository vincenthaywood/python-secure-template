# 🔒 Python Secure Template

A production-ready Python template with enterprise-grade security scanning, CI/CD pipeline, and best practices built-in.

## ✨ Features

### 🛡️ **Enterprise Security**
- **Automated vulnerability scanning** with Safety, pip-audit, and Snyk
- **Security linting** with Bandit and Semgrep
- **Code security analysis** with CodeQL
- **Daily security monitoring** with scheduled scans
- **Dependency vulnerability tracking**
- **License compliance checking**

### 🚀 **Robust CI/CD Pipeline**
- **Multi-stage quality gates** (lint, type-check, test, build)
- **Security-first deployment** - only deploys after all security checks pass
- **Comprehensive Python tooling** (Black, isort, Flake8, MyPy)
- **Build verification** and package validation
- **Branch protection ready** workflows

### 🔧 **Developer Experience**
- **Python 3.11+** with modern features
- **Type checking** with MyPy
- **Code formatting** with Black
- **Import sorting** with isort
- **Comprehensive security tools** built-in
- **Detailed security documentation**

## 🚀 Quick Start

### 1. Use This Template
```bash
# Create new repository from this template
gh repo create my-secure-python-app --template vincenthaywood/python-secure-template

# Or clone directly
git clone https://github.com/vincenthaywood/python-secure-template.git my-app
cd my-app
```

### 2. Setup Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Install Development Dependencies
```bash
pip install -r requirements-dev.txt
```

### 4. Run Security Check
```bash
# Quick security overview
python -m safety check
python -m bandit -r .

# Comprehensive security audit
python -m pip-audit
```

## 🔐 Security Tools

### **Vulnerability Scanning**
```bash
python -m safety check          # Check for known security vulnerabilities
python -m pip-audit            # Audit packages for known vulnerabilities
python -m snyk test            # Snyk security scanning (requires token)
```

### **Security Code Analysis**
```bash
python -m bandit -r .          # Security linting for Python code
python -m semgrep --config=auto # Static analysis for security issues
```

### **Code Quality**
```bash
python -m black .              # Code formatting
python -m isort .              # Import sorting
python -m flake8 .             # Code linting
python -m mypy .               # Type checking
python -m pytest              # Run tests
```

## 🛠️ CI/CD Pipeline

The template includes a comprehensive CI/CD pipeline that runs on:
- **Push** to main, develop, or staging branches
- **Pull requests** to main branch
- **Daily schedule** at 2 AM UTC for security monitoring

### **Pipeline Stages**

1. **🔍 Security Scan**
   - Safety vulnerability checking
   - Bandit security linting
   - Snyk vulnerability scanning (if token provided)
   - Semgrep security analysis
   - CodeQL security analysis

2. **✅ Quality Checks**
   - Black code formatting validation
   - isort import sorting check
   - Flake8 linting
   - MyPy type checking
   - Pytest test execution

3. **🏗️ Build Verification**
   - Package build validation (if setup.py exists)
   - Sensitive data detection
   - Build artifact verification

4. **🔧 Dependency Analysis**
   - pip-audit vulnerability scanning
   - License compliance verification

5. **🚀 Deployment Readiness**
   - Comprehensive security validation
   - Safe deployment confirmation

## ⚙️ Configuration

### **Required GitHub Secrets (Optional)**
- `SNYK_TOKEN`: For enhanced vulnerability scanning (get from [Snyk.io](https://snyk.io))

### **Development Configuration**
Create configuration files as needed:
- `setup.cfg` or `pyproject.toml` for tool configuration
- `.env` for environment variables (use python-dotenv)
- `pytest.ini` for test configuration

### **Environment Variables**
- Use `.env` files for development
- Set environment variables in your deployment platform
- Add secrets to GitHub repository settings for CI/CD

## 🔧 Project Structure

```
├── .github/workflows/ci-cd.yml    # CI/CD pipeline
├── src/                           # Source code
├── tests/                         # Test files
├── requirements.txt               # Production dependencies
├── requirements-dev.txt           # Development dependencies
├── setup.py                       # Package configuration (optional)
├── SECURITY.md                    # Security documentation
└── README.md                      # This file
```

## 📚 Security Best Practices

### **✅ Included Protections**
- **SQL Injection**: Bandit detection
- **Code Injection**: Security linting
- **Insecure Dependencies**: Automated vulnerability scanning
- **Secrets in Code**: Static analysis detection
- **License Compliance**: Automated checking

### **🔒 Additional Recommendations**
1. **Enable GitHub Security Features**:
   - Dependabot alerts
   - Secret scanning
   - Security advisories

2. **Branch Protection Rules**:
   - Require status checks
   - Require up-to-date branches
   - Restrict push to main

3. **Environment Security**:
   - Use environment variables for secrets
   - Rotate API keys regularly
   - Monitor security logs

4. **Python-Specific Security**:
   - Keep Python version updated
   - Use virtual environments
   - Validate input data
   - Use secure coding practices

## 🚀 Deployment

### **Docker Deployment**
```dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["python", "-m", "your_app"]
```

### **Cloud Platforms**
The template works with:
- **Heroku**: Add `runtime.txt` with Python version
- **AWS Lambda**: Package with dependencies
- **Google Cloud Run**: Use provided Dockerfile
- **Azure Functions**: Configure with requirements.txt

## 🆘 Troubleshooting

### **CI/CD Pipeline Issues**
- **Snyk failures**: Add SNYK_TOKEN secret or remove Snyk steps
- **Bandit failures**: Review and fix security issues in code
- **Safety failures**: Update vulnerable dependencies
- **Type checking errors**: Fix MyPy type annotations

### **Local Development Issues**
- **Import errors**: Ensure virtual environment is activated
- **Security warnings**: Run security tools individually to identify issues
- **Dependency conflicts**: Use pip-tools for better dependency management

## 📈 What's Included

### **Security Dependencies**
- **safety**: Known vulnerability database checking
- **bandit**: Security linting for Python
- **semgrep**: Static analysis security tool
- **pip-audit**: Vulnerability scanner for Python packages

### **Development Dependencies**
- **black**: Code formatter
- **isort**: Import statement organizer
- **flake8**: Code linter
- **mypy**: Static type checker
- **pytest**: Testing framework

### **Requirements Files**
```
requirements.txt         # Production dependencies
requirements-dev.txt     # Development and security tools
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Run security checks: `python -m safety check && python -m bandit -r .`
4. Run quality checks: `python -m black . && python -m flake8 .`
5. Submit a pull request

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🔗 Related Templates

- [Next.js Secure Template](https://github.com/vincenthaywood/nextjs-secure-template) - Next.js version with similar security features

---

**🚀 Ready to build secure Python applications with confidence!**

This template provides enterprise-grade security scanning and CI/CD pipeline out of the box. Start building secure Python applications without spending weeks setting up security infrastructure.
