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
   - Syntax permitting, all files should begin with a comment detailing the current file's name and relative path within the project

7. **Github Actions Workflows**
   - Github Actions is the only available runtime for script execution
   - All workflows that execute scripts should depend on the test workflow passing
   - All workflows should have a `workflow_dispatch` event trigger
   - All workflows should include their own respective file path as a trigger path (i.e. workflows should fire after they are changed)
   - Persist outputs generated from workflows using the `stefanzweifel/git-auto-commit-action@v5` GHA
```

short version:

```markdown
## Conventions and Best Practices
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
- All workflows that execute scripts should depend on the test workflow passing
- All workflows should have a workflow_dispatch event trigger
- All workflows should include their own respective file path as a trigger path (i.e. workflows should fire after they are changed)
- Persist outputs generated from workflows using the `stefanzweifel/git-auto-commit-action@v5` GHA
- Syntax permitting, files should begin with a comment indicating that file's name and relative path from the project root
```

## Architecture Mapping

```
Enumerate decisions in this project's structure/design/whatever that we could consider documenting as ADRs. save your tokens, just list the titles of potential ADRs. Treat this as a motivating exercise to itemize decisions and assumptions in the codebase and architecture.
```

## TDD

Instead of iteratively repairing an LLM implementation riddled with bugs, treat it as pseudocode and start from the top. new conv, share the code + :

```
i think I may have boiled the ocean a bit here and built something really cool before even checking the math. refactor this so we can build up our final objects/behaviors incrementally and test both the math and implementation of each part of the process as we go.
```

## Checkpointing to pick up from a new conversation

```
before moving on to the next implementation, lay out the roadmap of implementations / incremental development you had planned. what would be the next priority to implement? what comes after that? let's document your plan to make it easier to pick up from later
```
```
inventory the project state and layout for me. I haven't migrated any of the content out of this discussion yet and I want to make sure I don't miss anything. in fact, if you could prioritize what order I should move things so I can also quickly see if anything is broken, that would be helpful too. obviously, we start with that setup workflow from earlier.
```

## planning ahead

```
start by proposing a sequence of incremental development steps that will permit us to integrate these changes reasonably quickly without boiling the ocean and trying to change too many things at once.
```

```
sketch out the project structure, interspersing appropriate wireframes, systems diagrams, pseudocode, and narrative descriptions.
```

```
explain what this is and how it works. intersperse narrative explanations with diagrammatic explanations and pseudocode as appropriate
```
