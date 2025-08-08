# Copilot Instructions for pr-labels Repository

## Repository Overview

This repository demonstrates and enforces PR labeling workflows through GitHub Actions. The main purpose is to showcase how to require pull requests to have labels before they can be merged, which helps with release notes generation and project organization.

## Key Files and Structure

- `.github/workflows/require_labels.yml` - GitHub Actions workflow that enforces PR labeling requirements and provides auto-labeling
- This workflow automatically adds appropriate labels based on file changes and ensures every PR has at least one label before allowing merge
- `README.md` - User-facing documentation for the repository
- `parrot-haiku.txt` - Example content file

## Development Guidelines

### Pull Request Requirements
- **All PRs must have at least one label** - this is enforced by the `require_labels.yml` workflow
- **Auto-labeling is provided** - the workflow automatically adds appropriate labels based on file changes
- Use descriptive labels that help categorize the type of change (e.g., `enhancement`, `bug`, `documentation`, `feature`)
- Labels may be added automatically, but you can add additional labels manually if needed

### Labels to Use
When working on this repository, the workflow automatically applies labels based on file patterns:

**Auto-applied labels:**
- `documentation` - automatically added for changes to `.md` files, `copilot-instructions`, or `README` files
- `enhancement` - automatically added for changes to `.github/workflows` files

**Additional labels you can use:**
- `bug` - for bug fixes
- `maintenance` - for maintenance tasks, dependency updates, etc.
- `feature` - for new feature development

### Workflow Context
- The repository uses GitHub Actions to enforce labeling with advanced auto-labeling capabilities
- The workflow uses `actions/github-script@v7` to:
  - Analyze changed files in each PR
  - Automatically add appropriate labels based on file patterns
  - Validate that at least one label exists before allowing merge
- Auto-labeling patterns:
  - Documentation files (`.md`, `copilot-instructions`, `README`) → `documentation` label
  - Workflow files (`.github/workflows`) → `enhancement` label
- This helps maintain organized release notes and change tracking

## Coding Standards

### YAML Files
- Use consistent indentation (2 spaces)
- Follow GitHub Actions best practices
- Include descriptive names for jobs and steps
- Ensure proper permissions are set (e.g., `contents: read`, `issues: write`, `pull-requests: write`)

### Markdown Files
- Use clear headings and structure
- Include examples where helpful
- Keep documentation up to date with changes

## Testing

When making changes to workflows:
1. Test workflow changes on a feature branch first
2. The workflow will automatically add appropriate labels based on file changes
3. Verify that the workflow behaves as expected for both auto-labeled and manually-labeled PRs
4. Check that the auto-labeling logic correctly identifies file patterns

## Common Tasks

### Adding New Label Requirements
If you need to modify the label requirements or auto-labeling logic:
1. Edit `.github/workflows/require_labels.yml`
2. Update the file pattern matching logic in the `script` section
3. Modify the `labelsToAdd` array logic for new patterns
4. Test the changes thoroughly with different file types
5. Update this documentation if the requirements change

### Troubleshooting Failed Checks
If the "Require PR Labels" check fails:
1. Check the workflow logs to see if auto-labeling occurred
2. Verify that the PR has at least one label assigned (either auto-applied or manual)
3. If auto-labeling didn't work, check if your file changes match the expected patterns:
   - `.md` files, `copilot-instructions`, or `README` changes should trigger `documentation` label
   - `.github/workflows` changes should trigger `enhancement` label
4. Add labels manually if auto-labeling doesn't cover your change type
5. Ensure the workflow has proper permissions to read PR data and modify labels

## Repository Purpose

This repository serves as an example of implementing PR labeling requirements with intelligent auto-labeling, which is useful for:
- Maintaining organized release notes through automatic categorization
- Reducing manual labeling overhead with smart file-pattern detection
- Categorizing changes for better project management
- Enforcing consistent contribution practices
- Demonstrating GitHub Actions workflow patterns with advanced scripting
- Showcasing automatic label assignment based on file changes