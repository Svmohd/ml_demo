# AI Copilot Instructions for mldemo

## Project Overview
This is a lightweight Python ML utilities library with core math functions and comprehensive test coverage. The project supports data science workflows using pandas, numpy, scikit-learn, and visualization libraries.

**Key files:**
- `math_utils.py` - Core utility functions (add, subtract)
- `test_math_utils.py` - Unit tests using pytest assertions
- `requirements.txt` - Python dependencies (pandas, numpy, matplotlib, seaborn, scikit-learn, jupyter)

## Architecture & Design Patterns

### Module Structure
- **Single-file utilities approach**: Core functionality is in `math_utils.py` with simple, pure functions
- **No external state**: Functions are stateless and deterministic (e.g., `add()`, `subtract()`)
- **Test co-location**: Tests are in `test_math_utils.py` alongside imports of the module

### Function Conventions
- Lowercase, descriptive function names (`add`, `subtract`)
- Parameters placed directly without type hints (though type hints would enhance clarity)
- Direct returns without intermediate variable assignments when possible

## Development Workflows

### Running Tests
```bash
pytest test_math_utils.py
```
Tests use standard `assert` statements for validation. Check `test_math_utils.py` for the exact test cases and expected behaviors.

### Environment Setup
- Python virtual environment: `.venv/` (conda environment also available in `.conda/`)
- Install dependencies: `pip install -r requirements.txt`
- All ML/data science libraries are pre-configured

## Project-Specific Patterns

### Testing Pattern
Tests directly import the module and assert exact values:
```python
import math_utils
assert math_utils.add(2,3) == 5
```
When adding new functions to `math_utils.py`, add corresponding tests to `test_math_utils.py` with edge cases (zero, negative numbers).

### Naming Conventions
- **Functions**: Use full words (`add`, `subtract` not `sub` or `add_`)
- **Test functions**: Prefix with `test_` followed by function name being tested

## Integration Points & Dependencies

### External Libraries
- **Data science stack**: pandas, numpy for array/data operations
- **ML pipeline**: scikit-learn for modeling
- **Visualization**: matplotlib, seaborn for plots
- **Notebooks**: Jupyter for interactive development

### No External Services
This is a standalone utility library with no API calls, database connections, or service dependencies.

## Key Guidance for AI Agents

1. **Keep functions pure**: New utilities should not depend on external state
2. **Test-driven approach**: Add tests alongside new functions in `test_math_utils.py`
3. **Follow existing style**: Match the simple, direct coding style in `math_utils.py`
4. **Import pattern**: Module imports are at the top of test files; use `module.function()` pattern
5. **No type hints currently**: While beneficial, maintain consistency with existing code style for now
