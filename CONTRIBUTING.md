# Contributing to Voting Application via Blockchain

Thank you for considering contributing to this project! This document provides guidelines for contributing.

## How to Contribute

### Reporting Bugs

If you find a bug, please create an issue with:
- Clear description of the problem
- Steps to reproduce
- Expected vs actual behavior
- Environment details (Solidity version, Truffle version, etc.)
- Relevant logs or error messages

### Suggesting Features

Feature requests are welcome! Please create an issue with:
- Clear description of the proposed feature
- Use case and benefits
- Potential implementation approach (if applicable)

## Development Setup

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/voting-app.git
   ```
3. Create a feature branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. Install dependencies and set up development environment as described in README.md

## Code Style Guidelines

### Solidity
- Follow the [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html)
- Use clear, descriptive variable and function names
- Add comments for complex logic
- Include NatSpec documentation for all public functions
- Keep functions focused and small

### JavaScript
- Use ES6+ syntax
- Use meaningful variable names
- Add comments for complex operations
- Follow standard JavaScript formatting (2-space indentation)

## Testing

- Write tests for all new features
- Ensure existing tests pass before submitting PR
- Run tests with: `npm test`
- Aim for high test coverage

## Commit Messages

Write clear, concise commit messages:
- Use present tense ("Add feature" not "Added feature")
- First line: brief summary (50 chars or less)
- Add detailed description if needed (after blank line)

Example:
```
Add vote withdrawal mechanism

Implements a new function allowing voters to withdraw their
vote before the election ends, improving flexibility.
```

## Pull Request Process

1. Update documentation to reflect any changes
2. Ensure all tests pass
3. Update README.md if needed
4. Create a Pull Request with:
   - Clear description of changes
   - Link to related issues
   - Screenshots (if applicable)
5. Wait for review and address feedback

## Code of Conduct

- Be respectful and constructive
- Welcome newcomers and help them learn
- Focus on what is best for the community
- Show empathy towards other community members

## Questions?

Feel free to create an issue with your question or reach out to the maintainers.

Thank you for contributing!
