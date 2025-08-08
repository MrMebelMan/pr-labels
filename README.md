# PR Labels

A demonstration repository showing how to enforce pull request labeling requirements using GitHub Actions.

## Overview

This repository implements a workflow that requires all pull requests to have at least one label before they can be merged. This helps with:

- 📋 Organized release notes generation
- 🏷️ Consistent change categorization  
- 📊 Better project management and tracking

## How It Works

The repository includes a GitHub Actions workflow (`.github/workflows/require_labels.yml`) that:

1. Triggers on pull request events (opened, synchronized, labeled, unlabeled)
2. Checks if the PR has any labels assigned
3. Fails the check if no labels are found
4. Displays which labels are present if the check passes

## Usage

### For Contributors

When creating a pull request:

1. **Add appropriate labels** to your PR after creation
2. Common labels to use:
   - `enhancement` - New features or improvements
   - `bug` - Bug fixes
   - `documentation` - Documentation changes
   - `maintenance` - Maintenance tasks
   - `feature` - New feature development

3. **Wait for checks to pass** before requesting review

### For Repository Maintainers

This workflow can be customized by modifying `.github/workflows/require_labels.yml` to:
- Require specific labels
- Allow certain exceptions
- Customize the failure message
- Add additional validation logic

## Development

For development guidelines and detailed information about working with this repository, see [.github/copilot-instructions.md](.github/copilot-instructions.md).

## License

This project is provided as-is for demonstration purposes.