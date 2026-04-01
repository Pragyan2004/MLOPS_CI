# MLOPS_CI - Power Calculator Streamlit App

## Overview
This is a simple Streamlit web application that calculates the **square**, **cube**, and **fifth power** of a user-provided integer. It demonstrates a basic MLOPS (Machine Learning Operations) CI pipeline setup with:

- Streamlit for the interactive UI
- Pytest for unit testing the core power calculation functions
- GitHub Actions for automated CI testing on push/PR to `main`

The project is lightweight and ready to run locally or deploy.

## Features
- Interactive number input via Streamlit
- Real-time computation of:
  - Square: `n²`
  - Cube: `n³`
  - Fifth Power: `n⁵`
- Comprehensive unit tests (including error handling for invalid inputs)
- GitHub CI workflow that installs dependencies and runs tests automatically

## File Structure
```
.
├── app.py              # Main Streamlit app
├── _test.py            # Pytest unit tests and helper functions
├── .github/workflows/ci.yaml  # GitHub Actions CI pipeline
├── .gitignore          # Standard Python ignores
└── README.md           # This file
```

## Prerequisites
- Python 3.9+ (matches CI setup)
- GitHub repository (for CI to work)

## Quick Start

### 1. Clone & Setup
```bash
# Clone the repo (if not already)
git clone <your-repo-url>
cd MLOPS_CI

# Create virtual environment (recommended)
python -m venv venv
# On Windows: venv\Scripts\activate
# On macOS/Linux: source venv/bin/activate

# Install dependencies
pip install streamlit pytest
```

### 2. Run the App
```bash
streamlit run app.py
```
- Opens in your browser (usually http://localhost:8501)
- Enter an integer and see the power calculations!

### 3. Run Tests Locally
```bash
pytest _test.py -v
```
Expected output: All tests pass (4 passed).

## CI/CD Pipeline
- **Trigger**: Push or PR to `main` branch
- **Actions**:
  1. Checkout code
  2. Setup Python 3.9
  3. Install `pytest` and `streamlit`
  4. Run `pytest _test.py`
- View runs: Go to your repo's **Actions** tab on GitHub

## Testing Details
Tests cover:
- `square(n)`, `cube(n)`, `fifth_power(n)` for n=2,3
- Invalid input (TypeError on strings)

Functions are defined in `_test.py` for testability (could be refactored to utils.py).

## Deployment
- **Streamlit Cloud**: Connect GitHub repo [here](https://share.streamlit.io/)
- **Heroku/Docker**: Add `Procfile` or `Dockerfile` as needed
- No external ML models; pure math ops

## Contributing
1. Fork & clone
2. Create feature branch: `git checkout -b feature/power-root`
3. Commit changes: `git commit -m 'Add square root calc'`
4. Push & PR: Tests run automatically!

## License
MIT License - feel free to use/modify.

## Troubleshooting
- **Streamlit not found**: Run `pip install streamlit`
- **Tests fail**: Check Python version (3.9+)
- **CI fails**: Verify `pytest` & `streamlit` in workflow

Enjoy powering up your numbers! ⚡

