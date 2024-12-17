# Prompts
Just a place to track and improve on versions of multi-purpose prompts I find myself regularly reusing.

# Coding

## General purpose code quality assurance

```markdown
## Development Guidelines

### Code Organization for LLM Interaction

Keep in mind these guidelines for effective collaboration with Large Language Models:

1. **Separation of Concerns**
   - Each package should have a single, clear responsibility
   - Minimize coupling and maximize cohesion.
   - Keep files short and focused on a single responsibility
   - If you find yourself using comments like "... rest remains the same" or "... etc", the file is too long
   - Files should be completely replaceable in a single LLM interaction
   - Long files should be split into logical components

3. **Dependencies**
   - All dependencies managed in `pyproject.toml`
   - Optional dependencies grouped by feature:
     ```
     [project.optional-dependencies]
     test = ["pytest", ...]
     site = ["markdown2", ...]
     all = ["pytest", "markdown2", ...]  # Everything
     ```

4. **Testing Standards**
   - Use pytest
   - CI/CD workflows should generally depend on tests passing

5. **Why This Matters**
   - LLMs work best with clear, focused contexts
   - Complete file contents are better than partial updates with ellipsis
   - Tests provide clear examples of intended behavior
   - Shorter files make it easier for LLMs to:
     - Understand the complete context
     - Suggest accurate modifications
     - Maintain consistency
     - Avoid potential errors from incomplete information

7. **Best Practices**
   - Aim for files under 200 lines
   - Each file should have a single, clear purpose
   - Use directory structure to organize related components
   - Prefer many small files over few large files
   - Consider splitting when files require partial updates
   - Write tests alongside new features
   - Syntax permitting, files should begin with a comment indicating that file's name and relative path from the project root
```
