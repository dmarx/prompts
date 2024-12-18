# Prompts
Just a place to track and improve on versions of multi-purpose prompts I find myself regularly reusing.

# Coding

## General purpose code quality assurance

```markdown
## Development Guidelines

### Code Organization for LLM Interaction

When developing this project (or using it as a template), keep in mind these guidelines for effective collaboration with Large Language Models:

1. **File Length and Modularity**
   - Keep files short and focused on a single responsibility
   - If you find yourself using comments like "... rest remains the same" or "... etc", the file is too long
   - Files should be completely replaceable in a single LLM interaction
   - Long files should be split into logical components
   - Aim for low coupling and high cohesion

2. **Dependencies**
   - All dependencies managed in `pyproject.toml`

3. **Testing Standards**
   - Use pytest
   - CI/CD workflows should generally depend on tests passing

4. **Why This Matters**
   - LLMs work best with clear, focused contexts
   - Complete file contents are better than partial updates with ellipsis
   - Tests provide clear examples of intended behavior
   - Shorter files make it easier for LLMs to:
     - Understand the complete context
     - Suggest accurate modifications
     - Maintain consistency
     - Avoid potential errors from incomplete information

5. **Best Practices**
   - Aim for files under 200 lines
   - Each file should have a single, clear purpose
   - Use directory structure to organize related components
   - Prefer many small files over few large files
   - Consider splitting when files require partial updates

6. **Project Conventions**
   - Use `loguru` for all logging
   - Use `fire` for CLI interfaces
   - use `omegaconf` for yaml
   - Prefer `pathlib` for file system operations
   - Type hints should use:
     - Built-in generics over typing module (PEP 585)
     - Union operator (`|`) over Optional (PEP 604)
   - Github Actions is the only available runtime for script execution
   - All workflows depend on tests passing
   - Persist outputs generated from workflows using the `stefanzweifel/git-auto-commit-action@v5` GHA
   - Syntax permitting, all files should begin with a comment detailing the current file's name and relative path within the project
```

short version:

```markdown
**Conventions and Best Practices**
   - Aim for files under 200 lines
   - Each file should have a single, clear purpose
   - Use directory structure to organize related components
   - Prefer many small files over few large files
   - Consider splitting when files require partial updates
   - Use `loguru` for all logging
   - Use `fire` for CLI interfaces
   - use `omegaconf` for yaml
   - Use `pytest` (no Codecov account) for unit tests
   - Prefer `pathlib` for file system operations
   - Type hints should use:
     - Built-in generics over typing module (PEP 585)
     - Union operator (`|`) over Optional (PEP 604)
   - Github Actions is the only available runtime for script execution
   - All workflows depend on tests passing
   - Persist outputs generated from workflows using the `stefanzweifel/git-auto-commit-action@v5` GHA
   - Syntax permitting, files should begin with a comment indicating that file's name and relative path from the project root
```
