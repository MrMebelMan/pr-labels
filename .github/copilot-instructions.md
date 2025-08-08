# Copilot Instructions for pr-labels Repository

## Repository Overview

This repository demonstrates and enforces PR labeling workflows through GitHub Actions. The main purpose is to showcase how to require pull requests to have labels before they can be merged, which helps with release notes generation and project organization.

## Key Files and Structure

- `.github/workflows/require_labels.yml` - GitHub Actions workflow that enforces PR labeling requirements
- This workflow checks that every PR has at least one label assigned before allowing merge

## Development Guidelines

### Pull Request Requirements
- **All PRs must have at least one label** - this is enforced by the `require_labels.yml` workflow
- Use descriptive labels that help categorize the type of change (e.g., `enhancement`, `bug`, `documentation`, `feature`)
- Label PRs promptly after creation to avoid failing checks

### Labels to Use
When working on this repository, apply appropriate labels such as:
- `enhancement` - for new features or improvements
- `bug` - for bug fixes
- `documentation` - for documentation changes
- `maintenance` - for maintenance tasks, dependency updates, etc.
- `feature` - for new feature development

### Workflow Context
- The repository uses GitHub Actions to enforce labeling
- The workflow script checks `pullRequest.labels` and fails if the array is empty
- This helps maintain organized release notes and change tracking

## Coding Standards

### YAML Files
- Use consistent indentation (2 spaces)
- Follow GitHub Actions best practices
- Include descriptive names for jobs and steps

### Markdown Files
- Use clear headings and structure
- Include examples where helpful
- Keep documentation up to date with changes

## Testing

When making changes to workflows:
1. Test workflow changes on a feature branch first
2. Ensure the PR has appropriate labels to pass the checks
3. Verify that the workflow behaves as expected for both labeled and unlabeled PRs

## Common Tasks

### Adding New Label Requirements
If you need to modify the label requirements:
1. Edit `.github/workflows/require_labels.yml`
2. Update the script logic as needed
3. Test the changes thoroughly
4. Update this documentation if the requirements change

### Troubleshooting Failed Checks
If the "Require PR Labels" check fails:
1. Check that the PR has at least one label assigned
2. If labels are assigned but check still fails, review the workflow logs
3. Ensure the workflow has proper permissions to read PR data

## Repository Purpose

This repository serves as an example of implementing PR labeling requirements, which is useful for:
- Maintaining organized release notes
- Categorizing changes for better project management
- Enforcing consistent contribution practices
- Demonstrating GitHub Actions workflow patterns